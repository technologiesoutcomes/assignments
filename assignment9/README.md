### Assignment 9

1. Read this AWS blog - https://aws.amazon.com/blogs/mt/create-immutable-servers-using-ec2-image-builder-aws-codepipeline/ and answer the following questions. <b>DO NOT IMPLEMENT THE SOLUTION - JUST READ IT AND MAKE SURE YOU UNDERSTAND IT</b>

   * Discuss how applications running in an Auto Scaling Group with a custom AMI are deployed and maintained. 
 Create a custom AMI: The first step is to create a custom AMI that contains all the necessary software, configurations, and dependencies required to run the application. This AMI will be used to launch instances in the ASG.

2. Configure the ASG: Next, configure the ASG to use the custom AMI as the base image for launching instances. Set the desired capacity, minimum and maximum number of instances, and other parameters as needed.

3. Launch instances: The ASG will automatically launch instances based on the custom AMI and scale up or down as needed based on demand.

4. Monitor and maintain instances: It is important to monitor the instances running in the ASG for any issues or failures. This can be done using monitoring tools such as Amazon CloudWatch. If an instance fails, the ASG will automatically launch a new instance to replace it.

5. Update the custom AMI: As new versions of the application or dependencies become available, update the custom AMI accordingly. This can be done manually or using automation tools such as AWS Systems Manager.

6. Roll out updates: Once the custom AMI has been updated, roll out the updates to the instances in the ASG. This can be done using rolling updates or blue-green deployments
   * Why are immutable deployments preferred over mutable deployments?
   * What analogy is generally used to describe mutable and immutable deployments?
   * What do you understand by the concept of a Golden Image?


2. Imagine on your first week at a job your boss gave you the following GitHub repository to study and work on;

https://github.com/aws-samples/amazon-ec2-image-builder-samples

Navigate to all the folders and read all the code and try to understand what it is doing. Answer the following questions;
<b>DO NOT IMPLEMENT THE SOLUTION - JUST READ IT AND MAKE SURE YOU UNDERSTAND IT</b>

* Describe in details what you think this repository delivers.

* If you had to implement the content of this repository, develop a detailed plan of action but do not implement it.

* Cast yourself as an interviewee where you had to explain this repository and the infrastructure it creates. 
Write a narrative as to how you would go about describing your experience of working with this repository. (1000 words)


## References

* https://aws.amazon.com/image-builder/

* https://aws.amazon.com/blogs/compute/executing-ansible-playbooks-in-your-amazon-ec2-image-builder-pipeline/


