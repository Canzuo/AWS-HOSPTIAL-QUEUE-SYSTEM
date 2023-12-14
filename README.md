# AWS-HOSPTIAL-QUEUE-SYSTEM
Building a data processing pipeline for a hospital, including a system for patients to get a number online and receive SMS notifications, can be achieved using various AWS services.
This Project is supported with the help of ChatGPT 3.5.

**Step 1 - AWS Lambda:**
Using Lambda functions to handle the logic for generating and managing patient numbers.
Implementing a Lambda function to send SMS notifications.

**Step 2 - Amazon API Gateway:**
Setting up an API Gateway to expose endpoints for patients to get a number online and for the hospital to manage the queue.

**Step 3 - Amazon DynamoDB:**
Using DynamoDB to store patient information, including their assigned numbers and contact details.

**Step 4 - Amazon SNS (Simple Notification Service):**
Utilizing SNS to send SMS notifications. You can trigger this from Lambda functions when updating the queue.

**Step 5 - AWS Step Functions:**
Designing a Step Function to orchestrate the flow of processing. For example, when a patient gets a number, it triggers a series of Lambda functions and updates in DynamoDB, followed by an SMS notification.

**Step 6 - Amazon Cognito:**
Using Cognito for user authentication if patients need to log in or provide details.

**Step 7 - AWS CloudWatch:**
Setting up CloudWatch for logging and monitoring.

**Step 8 - Amazon S3:**
Optionally, use S3 for storing any static assets or logs.

# BASIC FLOW:
- The patient requests a number through the API Gateway.
- The lambda function processes the request, assigns a number, and updates DynamoDB.
- Another Lambda function triggers an SNS notification for the patient.
- The hospital staff manages the queue through another set of API Gateway endpoints.
- A Step Function may orchestrate the overall process, ensuring data consistency.

# STEP BY STEP
**Step 1: Set up AWS account**
- Set up AWS account at AWS Management Console

**Step 2: Create IAM Role**
- Create IAM Role with necessary permissions for the Lambda function.
- Attach 'AWSLambdaBasicExecutionRole' and 'AWSLambdaRole'

**Step 3: Set up DynamoDB**
- Create a new table in DynamoDB
- Create additional fields
- Enable DynamoDB streams
