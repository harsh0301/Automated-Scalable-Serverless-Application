# Serverless Email based User Authentication #

This AWS Lambda function, triggered by an SNS (Simple Notification Service) event, is designed for email verification and token storage in DynamoDB. It first parses the message received from the SNS event, extracts the email and token information, and calculates an expiration time for the token. 

The function then creates an item to store in a DynamoDB table containing the user's email, token, and expiration time. It logs the result of this operation.

Next, the function constructs an HTML email with an embedded verification link that's valid for 5 minutes. It sends this email to the specified email address using Amazon SES (Simple Email Service).

In summary, this Lambda function processes email verification requests, stores verification tokens in DynamoDB, and sends a time-sensitive email with a verification link to the user's email address.
