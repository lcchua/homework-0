_Q1: You want to build and deploy code functions in the AWS Cloud, but do not want to manage the infrastructure - Which of the following services can help meet this requirement?_<br>
A - AWS EC2<br>
B - AWS API Gateway<br>
**C - AWS Lambda**<br>
D - AWS DynamoDB

_Q2: You currently have a set of Lambda functions which have business logic embedded in them. You want customers to have the ability to call these functions via HTTPS. How can this be achieved?_<br>
**A - Use the API Gateway and provide integration with the AWS Lambda functions.**<br>
B - Enable HTTP access on the AWS Lambda functions.<br>
C - Add EC2 Instances with an API server installed. Integrate the server with AWSLambda functions.<br>
D - Use S3 websites to make calls to the Lambda functions

_Q3: A company wants to build a brand new application on the AWS Cloud. They want to ensure that this application follows the Microservices architecture. Which of the following services can be used to build this sort of architecture? Except?_<br>
A - AWS Lambda<br>
B - AWS ECS<br>
C - AWS API Gateway<br>
**D - AWS Config**

_Q4: Which AWS CLI command invokes a function?_<br>
A - aws lambda invoke --function ReturnBucketName outputfile.txt<br>
B - aws lambda execute --function-name ReturnBucketName outputfile.txt<br>
**C - aws lambda invoke --function-name ReturnBucketName outputfile.txt**<br>
D - aws lambda execute --function ReturnBucketName outputfile.txt

_Q5: What adds tracing capabilities to a Lambda?_<br>
A - AWS Trace<br>
B - CloudStack<br>
C - CloudTrail<br>
**D - AWS X-Ray**

_Q6: How can a developer provide Lambda code?_<br>
A - by uploading a .zip file<br>
**B - all of these answers**<br>
C - by editing inline<br>
D - from an S3 bucket

_Q7: You are performance-testing your Lambda to verify that you set the memory size adequately. Where do you verify the execution overhead?_<br>
A - CLoudWatch logs<br>
B - DynamoDB logs<br>
C - S3 logs<br>
**D - Lambda logs.**

_Q8: You need to use a Lambda to provide backend logic to your website. Which service do you use to make your Lambda available to your website?_<br>
A - S3<br>
**B - API Gateway**<br>
C - X-Ray<br>
D - DynamoDB

_Q9: What is AWS best practice for Lambda configuration?_<br>
**A - Overprovision memory to run your functions faster and reduce your costs. Do not overprovision your function timeout settings.**<br>
B - Overprovision memory and your function timeout settings to run your functions faster and reduce your costs.<br>
C - Do not overprovision memory. Overprovision your function timeout settings to run your functions faster and reduce costs.<br>
D - Do not overprovision memory. Do not overprovision your function timeout settings to run your functions faster and reduce costs.

_Q10: How do you stop a running Lambda that is stuck in a recursive loop?_<br>
A - Delete the function.<br>
**B - Set the function concurrent execution limit to 0 while you update the code.**<br>
C - Reset the function.<br>
D - Set the function concurrent execution limit to 100 while you update the code.
