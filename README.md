
A fully codified and one-click CloudFormation template to create a monitor for your Freifunk Access Point.

## Features / How it works

 - Regularly polls the Freifunk API for the Access Point status via CloudWatch Events
 - ends metric to a custom CloudWatch metric
 - An CloudWatch Alarm notifies you via SNS/E-mail


## Known issues

 - Currently only Hamburg is supported as the format of the real time APIs seem to differ from community to community.
 - Minimum of 2 minute check interval because of AWS madness with `rate` syntax which requires singular for `1`
 - The Lambda function itself has no monitoring currently, so we need either monitoring for it our adjust the existing CloudWatch alarm to react on `UNSUFFICIENT_DATA`
