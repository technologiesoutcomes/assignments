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

1. What are Kubernetes Operators? 
Kubernetes Operators extend Kubernetes by automating the management of specific applications or services.
Operators use custom resources and controllers to define and enforce the desired state of the application.
They encapsulate operational knowledge and best practices, simplifying complex application deployments.
Operators enable consistent and reliable application lifecycle management in a declarative manner.
They enhance automation, scalability, and fault tolerance for stateful applications on Kubernetes.

2. What are Kubernetes CRD?
Kubernetes Custom Resource Definitions (CRDs) enable the creation of custom resource types in Kubernetes.
CRDs extend the Kubernetes API to accommodate application-specific concepts and configurations.
CRDs allow users to define, manage, and interact with custom resources alongside built-in Kubernetes resources.
CRDs are often used in conjunction with Kubernetes Operators to automate the management of custom resources.
CRDs provide flexibility and extensibility, empowering users to tailor Kubernetes to their specific application requirements.

3. What are Kubernetes Controllers
Kubernetes Controllers are control loops that monitor and manage the state of resources in a Kubernetes cluster.
They ensure the desired state of resources matches the actual state by taking appropriate actions.
Controllers handle scaling, reconciliation, and lifecycle management of various resources.
They are implemented as Kubernetes deployments and run as part of the cluster control plane.
Controllers play a vital role in maintaining stability, reliability, and resilience of applications on Kubernetes.

## Linux administration and shell scripting

Research the following Linux commands

1. tar

Used to create, view, and extract files from tar archives. It combines multiple files into a single archive for easier storage or distribution.

2. rsync

A powerful file synchronization and transfer tool that efficiently copies and synchronizes files between different locations, either locally or over a network.

3. chown

Changes the ownership of files or directories, allowing you to transfer ownership to a different user or group.

4. curl

 A command-line tool to transfer data to or from a server using various protocols. It supports downloading or uploading files, making HTTP requests, and more.

5. systemctl

A command used to control and manage systemd services in Linux. It allows starting, stopping, restarting, and checking the status of services.

6. useradd

Creates a new user account on a Linux system.

7. usermod

Modifies existing user accounts, allowing you to change user attributes such as username, password, home directory, group membership, and more.

8. ln

 Creates links between files or directories. It can create hard links or symbolic links, which provide shortcuts to access files from different locations.

9. chmod

Changes the permissions of files or directories, controlling who can read, write, or execute them. It can modify permissions for the owner, group, and others.

10. chage

 Allows you to change the password aging and expiration settings for user accounts, enforcing password change policies and setting account expiration dates.

11. Explain what the following command does.
```
ssh-keygen -f mykeyfilename -t rsa -b 4096

```
The provided command generates an SSH key pair using the RSA algorithm with a key size of 4096 bits and saves it to a file named "mykeyfilename". SSH keys are commonly used for secure remote access and authentication to systems.

12. Explain what these permissions bits mean and translate them into the corresponding numeric value.

```
1) -rwxrwxrwx
2) -rw-r-xr-x
3) -r--r--r--
```
1) -rwxrwxrwx
User: Read, write, and execute permissions.
Group: Read, write, and execute permissions.
Others: Read, write, and execute permissions.
Numeric Value: 777

2) -rw-r-xr-x
User: Read and write permissions.
Group: Read permissions.
Others: Read and execute permissions.
Numeric Value: 754

3) -r--r--r--
User: Read permissions.
Group: Read permissions.
Others: Read permissions.
Numeric Value: 444

13. Which of these bits relate to symbolic link and which to a directory and which a simple file?
```
1) drwxrwxrwx
2) lrw-r-xr-x
3) -r--r--r--
```
1) Directory
2) Symbolic link
3) Simple file

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible


1. A simple three-tier java based application is deployed across two availability zones(AZ) on a Tomcat server. The application uses a self-managed PostgresQL database as its persistence layer and Nginx as its web server. The application is not required to be highly resilient nor be capable of elastic behaviour.

*  Describe how you might build this environment manually from the tool chain you are familiar with.

1) Design the architecture with separate tiers for presentation, application, and data.
2) Create a VPC and subnets for each tier, with appropriate network connectivity.
3) Provision EC2 instances for each tier, configure security groups, and consider using load balancers for scalability.
4) Implement Auto Scaling to adjust the number of instances based on demand.
5) Set up an RDS database in a private subnet for data storage.
6) Configure security measures like ACLs, security groups, and IAM roles.
7) Utilize CloudFront for content delivery to improve performance.
8) Monitor infrastructure components with CloudWatch and optimize based on usage patterns.

*  Describe how you might build this environment from an automated provisioning pipeline from the tool chain you are familiar with.

1) Set up Terraform environment and define AWS provider configuration.
2) Create VPC, subnets, and configure routing for networking.
3) Provision EC2 instances for each tier, specifying instance types, security groups, and user data.
4) Configure Auto Scaling groups to dynamically adjust instance numbers based on demand.
5) Set up RDS database instance with desired configuration.
6) Implement security measures using Terraform, such as security groups and IAM roles.
7) Enable content delivery through CloudFront for improved performance.
8) Set up monitoring and alerting using CloudWatch.
9) Apply Terraform configuration to provision the infrastructure.

2. Considering question 1 above, how would you re-design the application so that it is both elastic and highly available across the three tiers?

Use load balancers and containerization for the presentation tier to distribute traffic and scale dynamically.
Containerize the application logic in the application tier and implement auto-scaling and self-healing mechanisms.
Utilize managed database services with multi-AZ deployments and read replicas for the data tier.
Configure infrastructure across multiple availability zones for high availability.
Implement monitoring and automation tools to track performance, trigger scaling, and manage the infrastructure stack.

3. Describe how you would use Maven to build a java application

To use Maven to build a Java application:
1) Install Maven on your local machine.
2) Set up the project structure with source code and test directories.
3) Create a `pom.xml` file to define the project's configuration.
4) Specify dependencies in the `pom.xml` file.
5) Write Java code in the appropriate source code directory.
6) Build the project using `mvn clean package`.
7) Execute the application using the generated artifact.
Maven handles dependency management, compilation, testing, and packaging, providing a standardized build process for your Java application.


## System Architecture and Application Design, Cloud Computing (AWS)

1. Describe the role of each of these AWS Infrastructure component.

| Number | Subject                     | Role                                                                 |
| :---   | :----:                      | :---                                                                 |
| 1      | Global backbone             | AWS global backbone network infrastructure for high-speed data transfer between regions and availability zones.                   |
| 2      | Region                      | Geographical area with multiple availability zones where AWS resources are deployed.                                            |
| 3      | Availability zone (AZ)      | Physically separate data centers within a region that provide redundancy and fault isolation.                                 |
| 4      | Point of Presence (PoP)     | Physical location with networking equipment to improve the distribution of content and reduce latency for end-users.          |
| 5      | Co-location                 | Facility where multiple organizations can house their servers and network infrastructure for improved connectivity.           |
| 6      | Direct Connect              | Dedicated network connection between on-premises infrastructure and AWS, providing secure and reliable data transfer.        |
| 7      | VPC                         | Virtual Private Cloud that enables you to create an isolated virtual network environment within AWS.                          |
| 8      | Subnet                      | Subdivision of a VPC that allows you to organize resources and control network traffic between them.                          |
| 9      | AWS Public Domain Service   | DNS service provided by AWS to route internet traffic to your public-facing resources like websites or load balancers.        |
| 10     | Internet Gateway            | Enables communication between your VPC and the internet, allowing inbound and outbound traffic.                              |
| 11     | NAT                         | Network Address Translation allows instances in a private subnet to connect to the internet via a public subnet and an internet gateway. |
| 12     | Bastion Server              | A server that provides secure access to resources in a private subnet by acting as a gateway for SSH or RDP connections.     |

These components play various roles in AWS infrastructure, providing connectivity, isolation, redundancy, and security for your applications and resources.

2.  What role does the following AWS components play in a typical Three-tier Application design

| Number | Component               | Role                                                                                                                                                            |
| :---   | :----:                 | :---                                                                                                                                                            |
| 1      | External Load Balancer  | Routes incoming traffic from the internet to the web tier instances, providing scalability, fault tolerance, and distributing the load among multiple instances. |
| 2      | Internal Load Balancer  | Balances traffic between instances within the application tier, ensuring high availability and distributing the workload for improved performance.                |
| 3      | Multiple Availability Zones (AZ) | Ensures redundancy and fault tolerance by deploying resources across multiple data centers within different availability zones.                                 |
| 4      | Auto-scaling Group      | Automatically adjusts the number of instances in the web and application tiers based on demand, ensuring optimal resource utilization and application availability.    |
| 5      | Web Tier                | Hosts the front-end components of the application, handles user requests, and serves static and dynamic content to users.                                        |
| 6      | Application Tier        | Contains the business logic and processing components of the application, handling application-specific tasks and data processing.                            |
| 7      | Database (Master)       | Stores the primary copy of the application's data, handles write operations, and ensures data integrity.                                                      |
| 8      | Database (Slave)        | Replicates the data from the master database for read-heavy workloads, improving performance and enabling scalability by offloading read operations.             |


3. An AWS customer wants to connect their on-premise datacenter to their VPC network in AWS. Describe the ways in which this could be achieve?

To connect an on-premises datacenter to a VPC network in AWS:
- Use AWS Site-to-Site VPN or AWS Client VPN to establish an encrypted tunnel over the internet.
- Utilize AWS Direct Connect for a dedicated network connection with higher bandwidth and lower latency.
- Set up AWS Transit Gateway as a central hub for connecting multiple VPCs and the on-premises network.
- Employ AWS Direct Connect Gateway to connect multiple Direct Connect connections to different VPCs and the on-premises network.
- Establish VPC peering to enable direct communication between the AWS VPC and the on-premises network using private IP addressing.
- Use AWS Route 53 Resolver for seamless DNS resolution between the on-premises network and the VPC.

The specific choice of connectivity method depends on factors such as bandwidth requirements, security needs, and network architecture. Customers can select the most suitable solution or combination of solutions to connect their on-premises datacenter with their AWS VPC network.

4. An AWS customer can build services using components from the AWS public domain as well as services deployed in the customer's VPC and datacentre. Name some AWS services that run in the public domain and how they might be integrated with services in the VPC and in the on-premise datacentre.

AWS services that run in the public domain and can be integrated with services in a customer's VPC and on-premises datacenter include:

- **Amazon S3 (Simple Storage Service)**: Provides object storage in the cloud. It can be accessed from both the VPC and on-premises environments, allowing seamless storage integration between the two.

- **Amazon RDS (Relational Database Service)**: Offers managed database services like MySQL, PostgreSQL, Oracle, and SQL Server. RDS databases can be accessed from both the VPC and on-premises datacenters, enabling hybrid database setups.

- **Amazon Redshift**: A fully managed data warehousing service. It can be integrated with on-premises data sources and accessed from the VPC, allowing data consolidation and analysis across environments.

- **AWS Lambda**: A serverless compute service. Lambdas can be triggered by events from both the VPC and on-premises systems, enabling integration and execution of serverless functions.

- **Amazon SQS (Simple Queue Service)**: A fully managed message queuing service. It can be used as a communication mechanism between services in the VPC and on-premises components, facilitating decoupling and asynchronous processing.

- **AWS Direct Connect**: Provides dedicated network connections between on-premises datacenters and AWS. It allows secure and reliable communication between the VPC and the on-premises network, enabling hybrid cloud architectures.

- **Amazon Route 53**: A scalable and highly available DNS service. It can be used to route traffic between the VPC, on-premises resources, and public-facing services, ensuring seamless name resolution and connectivity.

By leveraging these services, customers can integrate their VPC and on-premises environments with AWS services in the public domain, creating a hybrid architecture that combines the benefits of cloud computing with their existing infrastructure.

5. With respect to AWS cloud services explain what each of these mean;

Here is a summary of the AWS cloud service models:

- **Infrastructure as a Service (IaaS)**: Provides virtualized computing resources for users to manage their own infrastructure, such as Amazon EC2 and Amazon S3.

- **Platform as a Service (PaaS)**: Offers a platform for application development and management without the complexity of infrastructure management, like AWS Elastic Beanstalk and AWS Lambda.

- **Software as a Service (SaaS)**: Delivers software applications over the internet, eliminating the need for local installation and maintenance, such as Amazon WorkSpaces and Amazon S3 Glacier.

- **Managed Services**: Fully managed offerings that handle administrative and operational tasks for users, such as Amazon RDS and AWS Managed EKS.

- **Serverless Services**: Abstract server management, enabling users to focus on code without provisioning or managing servers, like AWS Lambda and Amazon API Gateway.

- **Self-Managed Services**: Require users to manage and maintain the infrastructure and software components, such as EC2 instances and Amazon EKS.



6. In terms of their geographical location and distribution, AWS services can be roughly categorised as Global, Regional and Zonal. What do you understand by this classification?

AWS services can be categorized as Global, Regional, and Zonal based on their geographical location and distribution:

- **Global Services**: These are services that are available and accessible globally, irrespective of specific AWS regions. Examples of global services include AWS Identity and Access Management (IAM) and AWS CloudFront, which provide identity and access management and content delivery network services, respectively, across all AWS regions.

- **Regional Services**: These are services that are specific to a particular AWS region. They are designed to cater to the needs of customers within that region. Examples of regional services include Amazon RDS and Amazon S3, which provide managed database and object storage services, respectively, within a specific AWS region.

- **Zonal Services**: These are services that are deployed at the level of individual availability zones (AZs) within an AWS region. Availability zones are isolated data centers within a region that are designed to be independent of each other in terms of power, cooling, and networking. Zonal services operate within a single AZ and provide services with high availability and fault tolerance. Examples of zonal services include Amazon EC2 instances and Amazon RDS Read Replicas, which are deployed within specific AZs to provide compute and database replication capabilities.


7. Complete the table below, naming some services in the corresponding category

| Number      |           Global services                 | Regional services          |    Zonal services                  |
| :---        |            :----:                         | :---                       |    :---                            |
| 1  | AWS IAM (Identity and Access Management)         | Amazon S3                  |    Amazon EC2                      |
| 2  | AWS CloudFront                                   | AWS Lambda                 |    Amazon RDS                      |
| 3  | Amazon Route 53                                  | AWS Elastic Beanstalk      |    Amazon EBS                      |
| 4  | AWS CloudFormation                               | Amazon Redshift            |    Amazon EC2 Auto Scaling         |
| 5  | Amazon S3 Glacier                                | AWS Elastic Load Balancer  |    Amazon EFS                      |
| 6  | AWS Direct Connect                               | Amazon RDS Aurora          |    Amazon EMR                      |
| 7  | AWS CloudTrail                                   | AWS IoT Core               |    Amazon DynamoDB                 |


8. What do you understand by the term <b> Authentication </b> and describe how you authentication to the following systems;
  **Authentication** refers to the process of verifying the identity of a user or system to ensure authorized access to resources. 

- **AWS Console**: Authentication to the AWS Console involves providing valid username/password credentials or using Single Sign-On (SSO) solutions like AWS Identity and Access Management (IAM) roles, federated logins, or Multi-Factor Authentication (MFA).
- **AWS API**: Authentication to the AWS API typically involves generating an access key and secret key pair, which are used to sign API requests. This can be done through AWS IAM, where the access keys are associated with an IAM user or IAM role.
- **Ubuntu server running in AWS using SSH keys**: Authentication to an Ubuntu server in AWS involves generating an SSH key pair, where the public key is added to the server's authorized keys file, and the private key is used for authentication when connecting via SSH.
  
9. What do you understand by the term <b> Authorisation </b> and describe how you might set up authorisation to the following systems;
  
  **Authorization** refers to the process of granting or denying access to resources based on the authenticated identity and the permissions associated with that identity.

- **AWS Console**: Authorization in the AWS Console is managed through AWS Identity and Access Management (IAM). It involves creating IAM policies that define the permissions and access levels for individual IAM users or groups. These policies can control access to specific AWS services, resources, or actions.

- **AWS API**: Authorization to the AWS API is enforced using AWS IAM policies as well. By configuring IAM policies, you can grant or restrict access to specific API actions and resources based on the IAM user or role's permissions. IAM policies can be attached to users, groups, or roles to control API access.

- **An AWS Linux server**: Authorization on an AWS Linux server can be set up by managing user accounts, groups, and file permissions. Users can be added to specific groups, and group permissions can be configured using file system permissions (such as chmod) to control access to files and directories. Additionally, tools like AWS Identity and Access Management (IAM) can be used to manage SSH access to the server, allowing only authorized users to connect.

10. Explain what these two AWSCLI commands do. What could you say about the relation between a security group and an EC2 instance?

```
1) aws ec2 create-security-group --group-name MySecurityGroup --description "My security group" --vpc-id vpc-1a2b3c4d

2) aws ec2 modify-network-interface-attribute --network-interface-id eni-686ea200 --attachment AttachmentId=eni-attach-43348162,DeleteOnTermination=false
```

Relation between a security group and an EC2 instance:
A security group acts as a virtual firewall that controls inbound and outbound traffic for an EC2 instance. It acts as a rule set that defines which network traffic is allowed to access the EC2 instance. Each EC2 instance must be associated with one or more security groups. The security group rules define the protocols, ports, and IP ranges that are allowed to access the EC2 instance. The security group and EC2 instance are tightly linked, as the security group rules apply specifically to the associated EC2 instance, ensuring that only authorized traffic is allowed to reach the instance.

1)  creates a new security group in AWS EC2

2)  Modifies the attributes of a network interface in AWS EC2


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

