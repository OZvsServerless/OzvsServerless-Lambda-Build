# aws-cf-createApprovalEntry-build
This codebase is created to experiment with AWS Lambda. The goal is to use SAM to deploy and publish the lambda function using Cloud formation.

## Setup
- Setup AWS CLI (details see https://docs.aws.amazon.com/lambda/latest/dg/setup-awscli.html)
- Setup SAM Local (details see https://docs.aws.amazon.com/lambda/latest/dg/sam-cli-requirements.html)
- Install NodeJS and NPM
- Clone the repo
- Run "npm install"

## CI/CD
Create AWS Code Pipeline for this repo. The source code already contains "buildspec.yml" file that can be used to provide build instructions to CodeBuild service. For details see buildspec.yml file.

## Unit Tests
Run "npm test" to execute unit tests

## Functional Tests
Generate S3 event using:

sam local generate-event s3 --bucket localTestBucket  --key test-key > event_file.json

sam local invoke AddReviewDocumentToList -e event_file.json
