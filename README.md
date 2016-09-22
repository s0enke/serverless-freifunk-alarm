# Serverless Freifunk Monitor with AWS CloudWatch and Lambda

A fully codified and one-click CloudFormation template to create a monitor for your Freifunk Access Point.

## Features / How it works

 - Regularly polls the Freifunk API for the Access Point status via CloudWatch Events
 - Sends status to a custom CloudWatch metric
 - An CloudWatch Alarm notifies you via SNS/E-mail

## How to use it

 - Open CloudFormation in your AWS console and create a new stack by uploading the `app.yaml` of this repository and follow the steps

## Known issues

 - Currently only Hamburg is supported as the format of the real time APIs seem to differ from community to community.
 - Minimum of 2 minute check interval because of AWS madness with `rate` syntax which requires singular for `1`
 - The Lambda function itself has no monitoring currently, so we need either monitoring for it our adjust the existing CloudWatch alarm to react on `UNSUFFICIENT_DATA`
 - Currently no direct launch link to CloudFormation provided as this would need the maintenance of a pipeline to push template to S3
