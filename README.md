# My Lex Bot

This project deploys an AWS Lex bot using the Serverless Framework and GitHub Actions. The bot is defined in the `bot-definition.json` file and the Serverless Framework configuration is in the `serverless.yml` file.

## Prerequisites

- AWS account with appropriate permissions to create and manage Lex bots.
- GitHub account to set up the GitHub Actions workflow.
- Node.js and npm installed on your local machine.

## Setup

1. Clone this repository to your local machine.

2. Install the Serverless Framework globally:

```bash
npm install -g serverless
```

3. Configure your AWS credentials. You can do this by setting up the AWS CLI and running `aws configure`, or by setting the `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment variables.

## Deployment

The bot is automatically deployed when changes are pushed to the main branch of the repository. The GitHub Actions workflow defined in `.github/workflows/deploy.yml` handles the deployment.

The workflow does the following:

- Checks out the repository.
- Sets up Node.js.
- Installs the project's npm dependencies.
- Runs `npx serverless deploy` to deploy the bot.

You can monitor the progress of the deployment in the Actions tab of the GitHub repository.

## Testing

After the bot is deployed, you can test it in the AWS Lex console. You can send messages to the bot and see its responses.

## Cleanup

To remove the bot, you can run `npx serverless remove`. This will delete the bot and all its associated resources from your AWS account.