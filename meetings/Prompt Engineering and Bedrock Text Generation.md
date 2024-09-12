# Prompt Engineering and Bedrock Text Generation

Notes from session hosted by AWS (Ashwin Raghuraman) and Riot Games (Tony Ou)

- Recieved one time access to Bedrock Workshop to practice and check everything out.
- Sagemaker- to create Jupyter Notebook
- Check Sagemaker
- <a href = "https://developer.riotgames.com/apis#val-content-v1">Valorant APIs</a>
- There should be an initial "world config" event, that gives a mapping of each players with their agent PUUIDs
- DataDragon to grab actual agent infor from the PUUID
- The tournament data isn't from data dragon - DataDragon is a separate public API riot has that returns mostly game assets (e.g. champions, agent, items) metadata
- A simple usable interface (i.e. chatbot) to interact with should be enough anything else would be a plus during judging!
- <a href = "https://aws.amazon.com/certification/certified-cloud-practitioner/">Cloud Practitioner Certification</a>: If interested in getting a beginner AWS certification.
- If `boto3_bedrock = boto3.client('bedrock')` gives error, make sure code is executed (and import boto3 to environment)
