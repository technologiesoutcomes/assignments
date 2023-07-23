1. Read the article on this link https://aws.amazon.com/blogs/aws/new-use-aws-privatelink-to-access-aws-lambda-over-private-aws-network and answer the following questions:

* Why would organisations be concerned about connecting to the Lambda service through its public API?
* What AWS service allows a service in your VPC to connect to the Lambda service?
* For security reasons your organisation has mandated that all Lambda functions connect to third party partner organisations through your VPC. Discuss how you would architect this solution.

Organizations may be concerned about connecting to the Lambda service through its public API because it can potentially expose sensitive data and increase the risk of security breaches. Additionally, public APIs may not provide the necessary level of control and customization required for certain use cases.

The AWS service that allows a service in your VPC to connect to the Lambda service is called VPC Endpoints for AWS Lambda. This service creates a private connection between your VPC and the Lambda service, allowing you to securely invoke Lambda functions without exposing them to the public internet.

To architect a solution where all Lambda functions connect to third party partner organizations through your VPC for security reasons, you would need to follow these steps:

1. Create a VPC with private subnets and configure a VPC endpoint for AWS Lambda.
2. Create a security group that allows outbound traffic to the partner organization's IP addresses and ports.
3. Create a Lambda function and configure it to use the VPC endpoint for AWS Lambda and the security group created in step 2.
4. In the Lambda function code, include the necessary code to connect to the partner organization's API using the appropriate credentials and endpoints.
5. Test and deploy the Lambda function.

2. Hashicorp Packer can be used to create custom AMI in AWS. Research this product thoroughly and implement the following:

* Install Packer on your local computer.
* Create the Packer configuration to create an AMI in your AWS accounts that bakes in an Nginx instance.
* Use the custom AMI with the Nginx to create an EC2 instance in your account and start up the Nginx and ensure it is accessible on the internet.
* Verify that it is accessible on the internet
* At the end of the exercise terminate the instance

