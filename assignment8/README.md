1. Read the article on this link https://aws.amazon.com/blogs/aws/new-use-aws-privatelink-to-access-aws-lambda-over-private-aws-network and answer the following questions:

* Why would organisations be concerned about connecting to the Lambda service through its public API?
* What AWS service allows a service in your VPC to connect to the Lambda service?
* For security reasons your organisation has mandated that all Lambda functions connect to third party partner organisations through your VPC. Discuss how you would architect this solution.


2. Hashicorp Packer can be used to create custom AMI in AWS. Research this product thoroughly and implement the following:

* Install Packer on your local computer.
* Create the Packer configuration to create an AMI in your AWS accounts that bakes in an Nginx instance.
* Use the custom AMI with the Nginx to create an EC2 instance in your account and start up the Nginx and ensure it is accessible on the internet.
* Verify that it is accessible on the internet
* At the end of the exercise terminate the instance

