# Serverless AWS CodeCommit Repository Event Notifier

A simple lambda function that gets triggerred in response to an AWS CodeCommit repository events and update the team in slack.

![Fig : Serverless AWS CodeCommit Repository Event Notifier](https://raw.githubusercontent.com/miztiik/serverless-code-commit-repo-event-notifier/master/images/serverless-code-commit-repo-event-notifier.png)


1. ## Configure Lambda Function

    - The python script is written(_and tested_) in `Python 3.7`.
    - `Copy` the code from `serverless-code-commit-repo-event-notifier` in this repo to the lambda function
    - _Optional:_ Add slack `slack_webhook_url` in the environment variable
    - `Save` the lambda function

1. ## Configure Lambda Triggers

    - Choose **AWS CodeCommit** from the list of services.

    ![Fig : Serverless AWS CodeCommit Repository Event Notifier](https://docs.aws.amazon.com/codecommit/latest/userguide/images/codecommit-lambda-trigger.png)

    - In **Repository name**, choose your repository name.

    - In **Trigger name**, enter a name for the trigger.
    - In **Events**, choose the repository events that trigger the Lambda function, for example, choose **All repository events**.
    - In **Branches**, Choose **All branches**, if you want the trigger to apply to all branches of the repository.
    - In **Custom data**, _Optional_: Leave empty for now.
    - Choose **Next**.

    Now your lambda function should be triggered when ever there is a CodeCommit event in your repository

1. Testing the solution

    Create a new commit/branch in your repo, you should be getting the message in Slack(if configured).
