# Setting up Development Environment

### AWS Setup

- AWS Credit Request: Ensure the request for $100 credits has gone through AWS.
- Amazon Bedrock Access: Verify that Amazon Bedrock services are accessible on account. Bedrock is crucial for LLM integration.
- Setting up AWS Services: We might need services such as-
    - <b>Amazon S3</b> for storing data
    - <b>Amazon Lambda</b> for serverless backend functions
    - <b>Amazon RDS/ DynamoDB</b> for database to store or query esports data.

### Local Development Environment

- Python/Node Setup (based on tech stack)
    - Python would most likely be useful for LLM integration with necessary libraries such as `boto3` (AWS SDK) and others such as `TensorFlow`, `PyTorch`, `Hugging Face Transformers`.
    - The Web backend/frontend would use Node.js, React or other frameworks.
 - Set up Environment Variables for AWS keys, Bedrock access, and any API keys for Riot's data sources.

### Set up Data Sources

- Use <a href = "resources/VCT Esports Data.md">resources</a> provided by Riot for this project.
- If possible, download sample datasets or mock data to work with while setting up integrations.

### Choose Development tools
- IDE/ Editor: Make sure everyone is using a common IDE for consistent development.
- AWS SDKs and CLI: Install the AWS SDK for the languages that will be used and set up the AWS CLI for easy access to AWS Services.

### Test Bedrock and Riot API Integration
Write a basic script to make sure you can:
- Call Riot API to successfully fetch player data.
- Use Bedrock for LLM Queries to ensure it responds correctly.
