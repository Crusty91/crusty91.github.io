---
title: "AWS Dev Lambda"
excerpt: "Demo on AWS Lambda"
toc: true
---

Lambda is a Serverless managed compute service from AWS.

## AWS Console

### Create a Lambda Function

1. Open AWS Console
1. Open Lambda service
1. Create function
    1. Browse serverless app repository
    1. Select *hello-world*
    1. Enter a valid identityNameParameter
    1. Deploy

### Test a Lambda Function

1. Open your Lambda function
1. Click on *Test App*
1. At the bottom, click on the function name
1. Click on Test
    1. Create a new event for testing
    1. Validate
1. Select event in drop down
1. Click on test
1. The function is executed and you can see traces and output.
1. You can edit the function with the built-in editor on the same screen
1. You can monitor your function using monitor tab

### Test a lambda function locally

1. [Install the AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)
1. got to your locally directory containing the function
    1. You can download my sample [here](({% link assets/files/lambda-hello-world-js %})
1. run the invoke command
```bash
sam local invoke helloworld -e .\testEvent.json
```