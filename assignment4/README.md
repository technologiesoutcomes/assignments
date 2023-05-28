## Key learnings, experience and your main selling points.

This section will be used to write your profile for your CV. So record your key learnings and experience on a weekly basis so we can track your progress and learning.

| Number      |           Subject              | What you have learnt this week and how might you describe this at an interview?   |
| :---        |            :----:              | :---  |
| 1  | Collaboration                           | YYYYYYYY   |
| 2  | Communication                           | YYYYYYYY   |
| 3  | Automation/CICD                         | YYYYYYYY   |
| 4  | AWS                                     | YYYYYYYY   |
| 5  | Kubernetes                              | YYYYYYYY   |
| 6  | Terraform                               | YYYYYYYY   |
| 7  | Linux                                   | YYYYYYYY   |
| 8  | System and Application Design           | YYYYYYYY   |
| 9  | Productivity                            | YYYYYYYY   |
| 10 | Yourself and your abilities             | YYYYYYYY   |


## Kubernetes, Docker, Containerisation and Virtualisation

With respect to Kubernetes define what the following entities mean.

1) Pod
2) Container
3) Node
4) Control plane
5) Data plane

## Linux administration and shell scripting

1) You have a shell script called addAccount.sh and you are trying to run the script but it is complaining that some permissions are missing. What would you do to fix that?
2) What Linux command would your use to find out what commands you have run in the past?
3) Research the following Linux commands
* chmod
* scp
* ssh

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible


1. You want to use the following code to created an AWS EKS resource from the 
public repository pointed to by the source clause. Would could you ensure
that any changes made to the public repository you are pointing to does not
adversely affect your infrastructure?

```
module "myeks" {
   source = "terraform-aws-modules/terraform-aws-eks"
   cluster_name = "mycluster"
}
```


2. When you run the terraform init command in the directory containing terraform files, what 
changes does it make to directory in which you run the command?


3. What is the purpose of a Terraform provider?


4. What is the purpose of Terraform state?


5. How would you ensure that the Terraform state is secure and can be used in a collaborative
environment with the rest of your team without it being corrupted?


6. You have created a resource using Terraform. A colleague of your accidentally changed the resource
on the AWS console. What would happen if you run the Terraform apply command again?


7. You have a Terraform file in which you have defined 10 resources. You realise that one of the resources 
is no longer required. How would you go about deleting the unwanted resource without deleting the other resources?


8. What is a Terraform backend and how might you configure one?


9. Describe the various method by which Terraform might obtain credentials it needs for authenticating to an endpoint?


10. Your terraform code uses public external modules. What do you need to do to ensure that these external modules dependencies 
are resolved before you provision your resources?

11. You have provisioned some infrastructure in the AWS cloud using Terraform. How could you check by querying the state what 
resources you have created using Terraform?

12. What is the recommended approach for editing the Terraform state?

13. Describe as best as possible what the following code does.
```
terraform {
  backend "s3" {
    bucket   = "techoutcomes-terraforms.tfstate"
    key      = "simplegithubactions"
    region   = "eu-west-1"
  }
}
```

14. Describe as best as possible what the following code does.
```
provider "aws" {
  region = local.region
}
```

15. What does is mean to lock and Terraform state file and why is it important to implement a locking mechanism for the state file?

16. Describe in details what each of the following Terraform command does;
a) terraform init
b) terraform apply --auto-approve
c) terraform fmt
d) terraform validate
e) terraform destroy

17. How would you name a file so that it is recognised by Terraform when you run terraform plan or apply?
18. What is the purpose of the Terraform plan command and why is it important to read carefully the output of the plan?
19. What Terraform concept would you use to ensure your code is re-useable?
20. Terraform provisioning are directory-oriented in the sense that the resources created in a "Terraform apply" are defined in the same directory and each directory maps to a state. You want to created three different environment (dev, test and production) from one directory containing the main Terraform definitions. How would you organise your file and directory system?
21. What do you understand by Terraform partial backend configuration?
22. What do you understand by the <b> Chicken-and-Egg </b> problem with respect to Terraform backend configuration and how is it generally solved.


## System Architecture and Application Design, Cloud Computing (AWS)

1. You have an application running on one server in the cloud serving requests from customers. There is a sudden increase in request from customers reaching the application and a lot of requests are failing or are extremely slow.
* Draw a diagram showing this architecture.
* How could you re-architect the application to allow it to handle more request?
* Draw a diagram of the new design.

2. You wish to SSH from you local laptop to your server in the AWS cloud. Describe the configuration you will need in place on your local laptop and on the AWS cloud to enable this.

3. What role does a database play in the overall business system design and what steps might you take to ensure the database is resilient and highly available?

4. Describe as best as possible what a three-tier architecture is? Which of the three tier would you deploy so that it is accessible to the internet?

5. Create a server (EC2 instance - Amazon Linux 2023, Free tier) in your AWS account and do the following.
* Log onto the EC2 instance from your local machine.
* Copy a file from your local machine onto the EC2 instance.
* What would you have to do to allow someone else to log onto your server?
* Add this public key into your authorised_key file
```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCkyNUp8esDy/6wOaBVo7Xq1JVuhuF3E8kQPWRAAdLPdbhwwpH2+SPuFoBF4Pk4RWkpNQMBZp+9uo9NNXB8PpHQxF5vFUrhJG8cmymdWdRG4YpXBOhThwU6TFo/qdz7E3oVYMkWAeuXgVpMRhwpHmy+Rv+JBx8g9Nc7UFMiMz1mHqYq7qCOaLGKBMWaw33Z3PUzZlNQk9MzM5wNaIOXg5QSEXaNNpQt0vyYbS5guVSLiN92UEypZqEwsqW2E1yUySjCkbCgO6kWVlYONUZqS9dVzi4QZ/DzwZWZz8hdYg8u1M+b3twmLlNHzZn9qkL5sP9c9SVj5eLFAarYgtAfg05t sunatrakey
```
* Shut down your server (do not terminate it). We shall be performing some tests on the machine later.

6. What is a bastion server and why is it required in some network architectures?
7. In terms of accessibility, what is the difference between a Public IP and a Private IP
8. Describe at a high level how the ssh system works.
9. When you create a key pair on AWS, describe where the keys are stored.
10. When you create an EC2 instance on AWS, a network interface is also created and a Private IP is attached with the interface. Describe why this is important.

## Site Reliability Engineering (SRE), Troubleshooting, Observability

1.

2.

3.

4.

5.



## DevOps and Agile Transformation principles and methodology

1.

2.

3.

4.

5.


## New commands logs - Enter up to ten new commands you have learnt this week

| Number      | Commands | What does it do and how might you check its effect     |
| :---        |    :----:   | :---  |
| 1  | XXXXXXXX       | YYYYYYYY   |
| 2  | XXXXXXXX       | YYYYYYYY   |
| 3  | XXXXXXXX       | YYYYYYYY   |
| 4  | XXXXXXXX       | YYYYYYYY   |
| 5  | XXXXXXXX       | YYYYYYYY   |
| 6  | XXXXXXXX       | YYYYYYYY   |
| 7  | XXXXXXXX       | YYYYYYYY   |
| 8  | XXXXXXXX       | YYYYYYYY   |
| 9  | XXXXXXXX       | YYYYYYYY   |
| 10 | XXXXXXXX       | YYYYYYYY   |

## Glossary of the week - Enter new technical words you have learnt this week and their meanings.

| Number   | Word | Meaning     |
| :---     | :----:   |  :---  |
| 1  | XXXXXXXX       | YYYYYYYY   |
| 2  | XXXXXXXX       | YYYYYYYY   |
| 3  | XXXXXXXX       | YYYYYYYY   |
| 4  | XXXXXXXX       | YYYYYYYY   |
| 5  | XXXXXXXX       | YYYYYYYY   |
| 6  | XXXXXXXX       | YYYYYYYY   |
| 7  | XXXXXXXX       | YYYYYYYY   |
| 8  | XXXXXXXX       | YYYYYYYY   |
| 9  | XXXXXXXX       | YYYYYYYY   |
| 10 | XXXXXXXX       | YYYYYYYY   |

