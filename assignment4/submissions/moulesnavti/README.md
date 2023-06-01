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

A pod in Kubernetes is the smallest and simplest unit of deployment. It represents a single instance of a running process in a cluster and encapsulates one or more containers, shared storage, network resources, and other configuration settings. Pods are scheduled and managed by the Kubernetes control plane, and they serve as the atomic unit for scaling, replication, and resource allocation within the cluster. Each pod has a unique IP address and can communicate with other pods using inter-pod networking.

2) Container

A container in Kubernetes refers to a lightweight and isolated runtime environment that encapsulates an application and its dependencies. It is a standardized unit of software packaging that includes everything needed to run an application, such as the code, runtime, system tools, libraries, and configurations. Containers provide a consistent and portable environment across different platforms and enable efficient resource utilization by sharing the host operating system kernel. In Kubernetes, containers are deployed and managed within pods, allowing for easy scaling, scheduling, and orchestration of containerized applications.

3) Node

A node is a worker machine within a cluster. Nodes run containerized applications and communicate with the control plane.
They have the necessary resources and services to manage containers.
Each node runs a kubelet agent to interact with the control plane and container runtime. Nodes can be scaled up or down to meet application demands.

4) Control plane

The control plane in Kubernetes manages the cluster and container orchestration.
It consists of components like the API Server, etcd, Scheduler, Controller Manager, and optional Cloud Controller Manager.
The API Server exposes the Kubernetes API and stores the cluster's state in etcd.
The Scheduler places containers onto nodes based on resource availability and scheduling policies.
The Controller Manager monitors the cluster's state and takes corrective actions to maintain the desired state.


5) Data plane

The data plane in Kubernetes is the runtime environment where containers are executed.
It consists of worker nodes and the container runtime running on those nodes.
Worker nodes host and manage the execution of containers within the cluster.
The container runtime pulls images, starts and stops containers, and manages their lifecycle.
The data plane works alongside the control plane to orchestrate containerized applications and ensure proper execution.


## Linux administration and shell scripting

1) You have a shell script called addAccount.sh and you are trying to run the script but it is complaining that some permissions are missing. What would you do to fix that?

  Make the file executable by using the following command <chmod +x addAccount.sh>

2) What Linux command would your use to find out what commands you have run in the past?

history

3) Research the following Linux commands
* chmod

chmod: The "chmod" command is used to change the permissions of files or directories in Linux.
Example: "chmod +x script.sh" makes the "script.sh" file executable.

* scp

scp: The "scp" command is used to securely copy files between local and remote systems or between remote systems.
Example: "scp file.txt user@example.com:/path/to/destination" copies "file.txt" to the remote system at "/path/to/destination".

* ssh

ssh: The "ssh" command is used to establish a secure shell connection to a remote server.
Example: "ssh user@example.com" connects to the remote server "example.com" as "user".

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible


1. You want to use the following code to created an AWS EKS resource from the 
public repository pointed to by the source clause. How could you ensure
that any changes made to the public repository you are pointing to does not
adversely affect your infrastructure?

a) Version Pinning: Specify a specific version or commit hash of the module you are using. This ensures that your infrastructure is built using a known and tested version of the module, regardless of any changes made to the repository in the future.
```
module "myeks" {
   source = "terraform-aws-modules/eks/aws"
   version = "x.x.x"  # Replace with the desired version or commit hash
   cluster_name = "mycluster"
}
```

b) Use a Private Fork: Create a private fork of the public repository and use the forked repository as the source. This allows you to have control over the changes made to the module and prevents unexpected changes from affecting your infrastructur

```
module "myeks" {
   source = "your-github-username/terraform-aws-eks"
   cluster_name = "mycluster"
}
```

2. When you run the terraform init command in the directory containing terraform files, what 
changes does it make to directory in which you run the command?

It creates auxiliary files and directories like .terraform.lock.hcl and .terraform/providers to manage dependencies and downloaded plugins. and also does the following 
The backend configuration is initialized for remote storage of the state.
Required provider plugins are downloaded and installed.
Remote modules referenced in the configuration are retrieved and stored locally.
Local state file is initialized to track infrastructure changes.


3. What is the purpose of a Terraform provider?
Terraform providers enable interaction with APIs, managing resources and bridging the gap between Terraform and target infrastructure. They define resource types, handle communication, and retrieve and compare resource states, allowing unified infrastructure management across platforms.


4. What is the purpose of Terraform state?


The purpose of Terraform state is to track and manage the current state of resources created by Terraform. It allows Terraform to plan and execute changes to infrastructure by:

Tracking resource state and storing information like IDs and attributes.
Managing dependencies and determining the order of resource creation and updates.
Detecting differences between desired and current state for change management.
Acting as a concurrency lock to prevent conflicts during concurrent operations.
Persisting state for collaboration and sharing among team members.
Overall, Terraform state is essential for managing infrastructure as code, ensuring desired state, tracking changes, and facilitating collaboration in Terraform projects.

5. How would you ensure that the Terraform state is secure and can be used in a collaborative environment with the rest of your team without it being corrupted?

To ensure a secure and collaborative Terraform state environment:

Use a remote state backend (e.g., AWS S3, Terraform Cloud) to store the state securely and centrally.
Implement access controls to restrict state access to authorized team members.
Enable versioning and auditing features to track changes and maintain accountability.
Regularly back up the state and create a disaster recovery plan.
Implement state locking to prevent concurrent modifications and conflicts.
Integrate Terraform with version control systems to track configuration changes.
These practices help safeguard the Terraform state, prevent corruption, and facilitate collaboration within the team.

6. You have created a resource using Terraform. A colleague of your accidentally changed the resource
on the AWS console. What would happen if you run the Terraform apply command again?


If a resource created by Terraform is manually modified in the AWS console:

Running terraform apply may result in an error if there is a conflict between the desired state and the actual state of the resource.
Terraform will not modify the resource to avoid unintended changes in case of a state conflict.
If the manually modified resource matches the desired state, terraform apply will recognize no changes are needed and will not modify the resource.
Terraform assumes control over resources it creates and manual modifications can cause state drift.
It is best practice to manage resources solely through Terraform or properly import existing resources into the Terraform state.


7. You have a Terraform file in which you have defined 10 resources. You realise that one of the resources 
is no longer required. How would you go about deleting the unwanted resource without deleting the other resources?

To delete an unwanted resource in Terraform without affecting other resources:

Identify the unwanted resource in your Terraform file.
Remove the resource block or configuration for the unwanted resource.
Run terraform plan to generate an execution plan.
Validate the plan to ensure only the unwanted resource will be deleted.
Execute terraform apply to apply the changes and delete the unwanted resource.
Verify that the unwanted resource is deleted while other resources remain intact.

8. What is a Terraform backend and how might you configure one?

A Terraform backend is responsible for storing the Terraform state file and facilitating remote operations. It determines where the state is stored and accessed, allowing for collaboration, state persistence, and advanced features. To configure a backend:

Choose a backend provider, such as AWS S3 or Terraform Cloud.
Add a backend configuration block to your Terraform configuration file, specifying the provider and relevant settings.
Run terraform init to initialize Terraform and set up the backend.
Configure credentials or authentication for the chosen backend provider.
Collaborate with your team by sharing the state file stored in the backend, ensuring synchronized state changes.
Configuring a backend ensures secure and centralized state storage, enabling collaboration and providing additional backend features for managing Terraform state.

'''
terraform {
  backend "s3" {
    bucket = "my-terraform-state-bucket"
    key    = "terraform.tfstate"
    region = "us-west-2"
  }
}
'''

9. Describe the various method by which Terraform might obtain credentials it needs for authenticating to an endpoint?


Terraform can obtain credentials for authentication to endpoints using different methods:

Environment variables, such as AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY.
Shared configuration files like the AWS CLI credentials file.
Provider-specific configuration blocks within the Terraform file.
Instance metadata service for cloud providers like AWS and Azure.
Integration with vaults or secret managers like AWS Secrets Manager or HashiCorp Vault.
Command-line input for manual credential entry.
The specific method depends on the provider and authentication requirements. Refer to the provider's documentation for proper configuration.

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

23. You want to use the Terraform public module "[terraform-aws-modules/ec2-instance/aws](https://github.com/terraform-aws-modules/terraform-aws-ec2-instance)" as shown in the code below. Go and look in the public module and fill in some of the interface value you will need in order to create the module
```
module "ec2_instance" {
  source = "terraform-aws-modules/ec2-instance/aws"

}
```

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

