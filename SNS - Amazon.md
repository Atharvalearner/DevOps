***# Simple Notification Service:***

* Amazon SNS is a fully managed messaging and notification service that sends messages or alerts to multiple subscribers simultaneously.
* It is commonly used for alerting, event-driven applications, and integrating AWS services.



***# Why do we use SNS?***

Send notifications through:

Email, SMS, Mobile push notifications, AWS Lambda, SQS, HTTP/HTTPS endpoints.



***# Example:***

A file is uploaded to S3.

↓

SNS sends an email: A new file has been uploaded.



**Another Example:**

CloudWatch detects: CPU > 90%

↓

SNS sends: Email, SMS, Mobile notification

