# VCT Esports Data - Technical Documentation

<a href = "https://docs.google.com/document/d/19H3FsWYEli6ShIV5_5fmhq2xDdfcQOCXlRiNvKZLYL8/edit?usp=sharing" rel = "nofollow"> Link to the official document </a>

<b> Last Updated:  5PM PST - 9/3/2024 </b>
<i> Please note that this is a living document, and could be updated throughout the Hackathon to reflect any frequently asked questions we might get from participants. </i>

Participants are provided with four sources of data in the S3 bucket:
- <b>Game data:</b> Events sent by the game server
- <b>Esports fixture data:</b> Information about the leagues, tournaments, players and teams
- <b>Esports mapping data:</b> Joins the livestats data with the esports fixture data
- <b>Fandom text data:</b> Community sourced text about Valorant esports (<a href = "https://valorant-esports.fandom.com/wiki/VALORANT_Esports_Wiki" rel = "nofollow">from VCT & VALORANT wiki</a>)
    - If using this data source, be sure to properly follow Fandom’s <a href = "https://www.fandom.com/licensing" rel = "nofollow">attribution requirements</a>

Participants do not need to utilize all sources of data for submissions. For example, the LLM could just use text data and optionally use game data to improve the model.

Please note that participants can also source their own data from the web, as long as it is used responsibly & within the terms of use stated on the websites. We are providing limited text data in our S3 buckets, so we encourage participants to scrape their own (e.g. VLR.gg).

## Game Data

Participants will have access to all time game data that has an associated esports mapping. Meaning, only live esports games (no public / tournament server games or scrim data will be made accessible). It should be noted that some event types have been added throughout the year, and some event schemas have evolved. Therefore, a participant’s program should be able to handle missing event types or fields. The game events will be sorted in chronological order.

This is a lot of data, and it's up to participants to decide what is relevant to them. The <b>Appendix</b> contains more details about event types, as well as an up to date example for each message type.

Each game is stored as a separate gzipped file in an <b>S3 bucket</b> and is named by the game's platform game ID, e.g. 
```{tournament}/games/val:004b09b1-4dc9-4185-baff-9b1c66b3ef99.json.gz```

## Esports Fixture Data

This is the metadata that contains information about players, teams, leagues and tournaments, and has been exported into respective files.

File names in S3:
- `{tournament}/esports-data/leagues.json.gz`
- `{tournament}/esports-data/tournaments.json.gz`
- `{tournament}/esports-data/players.json.gz`
- `{tournament}/esports-data/teams.json.gz`

### Important Notes
- Just because fixture data exists does not mean that the associated esports mapping or game data exists. For example, there could be fixture data referencing some VCT game, but the associated live stats file is either empty or does not exist.
    - Programs should be able to handle not finding an associated platform game ID for a given esports game ID
 
### Esports Mapping Data
The mapping data contains an esportsGameId as well as a platformGameId, which is how participants may join game data and esports fixture data together. The teamMapping field references the esports team IDs, from which participants can derive the team code and team name, and the participantMapping field references the esports player IDs.

Example game mapping:
```JavaScript
{
  "platformGameId": "val:cb611626-2910-46d3-8678-6501bf317f9f",
  "esportsGameId": "109711321499314292",
  "tournamentId": "109711321498527756",
  "teamMapping": {
    "18": "107722603442258744",
    "19": "105830904252954968"
  },
  "participantMapping": {
    "1": "106651749419114537",
    "2": "106651802407300792",
    "3": "107042219803278491",
    "4": "106652162020663630",
    "5": "106651747523026980",
    "6": "107735297326632949",
    "7": "106651763961975955",
    "8": "106651804162806952",
    "9": "106652153897244072",
    "10": "107723776556509563"
  }
}
```

Please note that the live stats game data refer to teams and players using the keys in `teamMapping` and `participantMapping` e.g. 18, 19 for teams or 1-10 for players.

The file name for the mappings export in the S3 bucket is: ```{tournament}/esports-data/mapping_data.json.gz```

## Fandom Text Data

There are 2 XML files available in the S3 bucket’s fandom folder. These XMLs contain all the text content of the <a href = "https://valorant.fandom.com/wiki/VALORANT">Valorant fandom</a> and <a href = "https://valorant-esports.fandom.com/wiki/VALORANT_Esports_Wiki">Valorant Esports fandom</a> sites. As LLMs rely heavily on text data, please feel free to include any other online sources for data if needed. Be sure to follow the website’s guidelines around use of data when doing so. 

## Other important notes about the data provided

### Events can be lost permanently
While we do our best to make sure all events are received and returned, we cannot guarantee all events, either because of bugs or events outside of our control (e.g. network issues, game / platform server crashes etc). Participants must be able to deal with lost events gracefully.
### Data Access
If using game data, we recommend that you start with the mappings file. Then, you can append any metadata you desire from the fixture data (i.e. `teamId` → teams, `participantId` → players, `tournamentId` → tournaments). The `platformGameId` should be used to access game data. Please note that it is not guaranteed that every `platformGameId` has an associated game file.
### Prettify
The game event JSON might be hard to read due to the data compression and extraction process with gzip. You can format / prettify the JSON using <a href = "https://jqlang.github.io/jq/">jq</a> and do something like:
```Unset 
jq '.' uglyFile.json > formattedFile.json
```

## Accessing the data from S3

S3 Bucket URL: s3://vcthackathon-data/

Here is the access pattern we recommend for downloading the data onto your local machine:

1. Download the esports fixture data as well as the mapping table
2. Iterate over the mapping table and get a list of platform game IDs for each tournament\
  a. Join tournament, team or participant data here if needed
3. For each platform game ID, download its associated game data file

Participants should note that downloading all the game data onto your local machine will require a <b>significant</b> amount of storage, as the entire dataset has a total size of <b>51.9 GB</b>. If you choose to download this data on your local machine you will need to be selective with what you download - consider only downloading a subset of the data, i.e. certain leagues or tournaments.

You can choose to visualize / use the data using standard code editors or tools such as AWS Athena. Data analytics such as Athena will require you to extract the gzipped folder. Since the provided data is separated by league, you could download a league (i.e. VCT international), cd into it and run a script to extract all the JSON data. Here is an example of a Python script you could use to extract game data of VCT internationals.

``` Python
import requests
import json
import gzip
import shutil
import time
import os
from io import BytesIO

# Insert desired league here (i.e. vct-international, vct-challengers, game-changers)
S3_BUCKET_URL = "TBD"


def download_gzip_and_write_to_json(file_name):
    if os.path.isfile(f"{file_name}.json"):
        return

    response = requests.get(f"{S3_BUCKET_URL}/{file_name}.json.gz")
    if response.status_code == 200:
        try:
            gzip_bytes = BytesIO(response.content)
            with gzip.GzipFile(fileobj=gzip_bytes, mode="rb") as gzipped_file:
                with open(f"{file_name}.json", 'wb') as output_file:
                    shutil.copyfileobj(gzipped_file, output_file)
                print(f"{file_name}.json written")
        except Exception as e:
            print("Error:", e)
    else:
        print(response)
        print(f"Failed to download {file_name}")


def download_esports_files():
    directory = "esports-data"
    if not os.path.exists(directory):
        os.makedirs(directory)

    esports_data_files = ["leagues", "tournaments",
                          "players", "teams", "mapping_data"]
    for file_name in esports_data_files:
        download_gzip_and_write_to_json(f"{directory}/{file_name}")


def download_games():
    start_time = time.time()
    with open("esports-data/mapping_data.json", "r") as json_file:
        mappings_data = json.load(json_file)

    directory = "games"
    if not os.path.exists(directory):
        os.makedirs(directory)

    mappings = {
        esports_game["platformGameId"]: esports_game for esports_game in mappings_data
    }

    game_counter = 0

    for esports_game in mappings_data:
        download_gzip_and_write_to_json(
            f"games/{esports_game["platformGameId"]}")
        game_counter += 1
        if game_counter % 10 == 0:
            print(f"----- Processed {game_counter} games, current run time: {
                  round((time.time() - start_time)/60, 2)} minutes")


if __name__ == "__main__":
    download_esports_files()
    download_games()
```
You will need Python 3.6 or higher to run the above code, as well as the requests module installed

