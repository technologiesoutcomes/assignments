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
ppn
1) Pod is the smallest unit in the kubernetes object model
2) Container is a lightweight portable executable package that contains all necessary depencies and configuration to run  specific software application
3) Node is a physical or virtual machine that runs one or more containers and provides necessary resources for it to operate
4) Control plane s the set of components in kubernetes that manages and control the overall state of the cluster
5) Data plane is the set off components in kuberneetes that handles the actual data traaffic and workload processing may

## Linux administration and shell scripting

1) You have a shell script called addAccount.sh and you are trying to run the script but it is complaining that some permissions are missing. What would you do to fix that? 
by mmaking the script executable using the command chmod +x addAccount.sh
2) What Linux command would you use to find out what commands you have run in the past? History command
3) Research the following Linux commands
* chmod change mode or permission of a file
* scp secure copy files from two remote hosts
* ssh secure shell to communicate or connect two remote hosts

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible


1. You want to use the following code to created an AWS EKS resource from the 
public repository pointed to by the source clause. How could you ensure
that any changes made to the public repository you are pointing to does not
adversely affect your infrastructure?

```
module "myeks" {
   source = "terraform-aws-modules/terraform-aws-eks"
   cluster_name = "mycluster"
}
```
by testing updates before implementing 
by setting up pipeline to automatically deploy  changes in the staging environment 
by using git version control tool to track changes
by precising the version constraint in the parameter

2. When you run the terraform init command in the directory containing terraform files, what 
changes does it make to directory in which you run the command?
Downloads any necessary plugins and stores in a .terraform directory it creates
Initializes the backend and sets up a state file


3. What is the purpose of a Terraform provider?
Its a plugin that allows terraform to interact with a specific cloud

4. What is the purpose of Terraform state?
To store the state of infrastructures mannaged by terraform

5. How would you ensure that the Terraform state is secure and can be used in a collaborative environment with the rest of your team without it being corrupted?
by storing in an s3 bucket

6. You have created a resource using Terraform. A colleague of your accidentally changed the resource
on the AWS console. What would happen if you run the Terraform apply command again? 
terraform will compare the resources in the state file and create one to reprovide whats in the state file


7. You have a Terraform file in which you have defined 10 resources. You realise that one of the resources local files is no longer required. How would you go about deleting the unwanted resource without deleting the other resources?
by deleting the resource from the terraform code

8. What is a Terraform backend and how might you configure one?
Its a way of storing terraform states out of  local files

9. Describe the various method by which Terraform might obtain credentials it needs for authenticating to an endpoint?
 Terraform can use environment variables to obtain credentials. For example, AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY can be set as environment variables to authenticate with AWS
Configuration files: Terraform can read configuration files, such as AWS CLI configuration files or Azure CLI configuration files, to obtain credentials.
IAM roles: If running on an EC2 instance or within an AWS ECS task, Terraform can use IAM roles to obtain credentials.
Instance metadata service: If running on an EC2 instance, Terraform can use the instance metadata service to obtain temporary credentials.
Keychain (macOS only): On macOS, Terraform can use the keychain to store and retrieve credentials.
HashiCorp Vault: Terraform can integrate with HashiCorp Vault to obtain and manage credentials securely.
CLI prompts: Terraform can prompt the user for credentials when running the apply command. However, this is not recommended for production use as it is less secure than other method


10. Your terraform code uses public external modules. What do you need to do to ensure that these external modules dependencies 
are resolved before you provision your resources? using the comand terraform init

11. You have provisioned some infrastructure in the AWS cloud using Terraform. How could you check by querying the state what 
resources you have created using Terraform?
using the command terraform plan

12. What is the recommended approach for editing the Terraform state?
It is not recomended to edit terraform state file

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
It specifies backend connfigurationnfor storinng terraform state file in an s3 bucket, key is the name of the bucket, and region where the bucket is located

14. Describe as best as possible what the following code does.
```
provider "aws" {
  region = local.region
}
```
provider specifies the provider type AWS with its region where it will be created

15. What does is mean to lock and Terraform state file and why is it important to implement a locking mechanism for the state file?
It means a single person can make changes to infrastructure

16. Describe in details what each of the following Terraform command does;
a) terraform init downloads and stores providers necessary plugins 
b) terraform apply --auto-approve deploys resources coded in the terraform main code
c) terraform fmt used to forat terraform configuration file
d) terraform validate checks the syntax and validity of terraform confguration files
e) terraform destroy destroys the terraform deployed resources

17. How would you name a file so that it is recognised by Terraform when you run terraform plan or apply? name.tf
18. What is the purpose of the Terraform plan command and why is it important to read carefully the output of the plan? gives details of the resources to be provisioned
19. What Terraform concept would you use to ensure your code is re-useable? modules
20. Terraform provisioning are directory-oriented in the sense that the resources created in a "Terraform apply" are defined in the same directory and each directory maps to a state. You want to created three different environment (dev, test and production) from one directory containing the main Terraform definitions. How would you organise your file and directory system?
main.tf
variables.tf
outputs.tf
dev/
    main.tf
    variable.tf
    outputs.tf
test/
    main.tf
    variable.tf
    outputs.tf
prod/
    main.tf
    variable.tf
    outputs.tf

21. What do you understand by Terraform partial backend configuration?
Its a feature that allows the configuration of each module backend and store state data in different s3 buckets or locations
22. What do you understand by the <b> Chicken-and-Egg </b> problem with respect to Terraform backend configuration and how is it generally solved. refers to the situation where terraform stores its state in a backend s3bucket, the s3 bucket is created throug another way like cli before terraform can store it state files which is provisioned by terraform

23. You want to use the Terraform public module "[terraform-aws-modules/ec2-instance/aws](https://github.com/terraform-aws-modules/terraform-aws-ec2-instance)" as shown in the code below. Go and look in the public module and fill in some of the interface value you will need in order to create the module
```
module "ec2_instance" {
  source = "terraform-aws-modules/ec2-instance/aws"

}
```

## System Architecture and Application Design, Cloud Computing (AWS)

1. You have an application running on one server in the cloud serving requests from customers. There is a sudden increase in request from customers reaching the application and a lot of requests are failing or are extremely slow.
* Draw a diagram showing this architecture.
* How could you re-architect the application to allow it to handle more request? adding external and inernal load balancers with auto scaling group
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
| 1  | scp       | YYYYYYYY   |
| 2  | ssh       | YYYYYYYY   |
| 3  | chmod       | YYYYYYYY   |
| 4  |        | YYYYYYYY   |
| 5  | XXXXXXXX       | YYYYYYYY   |
| 6  | XXXXXXXX       | YYYYYYYY   |
| 7  | XXXXXXXX       | YYYYYYYY   |
| 8  | XXXXXXXX       | YYYYYYYY   |
| 9  | XXXXXXXX       | YYYYYYYY   |
| 10 | XXXXXXXX       | YYYYYYYY   |

## Glossary of the week - Enter new technical words you have learnt this week and their meanings.

| Number   | Word | Meaning     |
| :---     | :----:   |  :---  |
| 1  | pods       | YYYYYYYY   |
| 2  | cluster       | YYYYYYYY   |
| 3  | EKS       | YYYYYYYY   |
| 4  | Node       | YYYYYYYY   |
| 5  | cloudformation       | YYYYYYYY   |
| 6  | XXXXXXXX       | YYYYYYYY   |
| 7  | XXXXXXXX       | YYYYYYYY   |
| 8  | XXXXXXXX       | YYYYYYYY   |
| 9  | XXXXXXXX       | YYYYYYYY   |
| 10 | XXXXXXXX       | YYYYYYYY   |

