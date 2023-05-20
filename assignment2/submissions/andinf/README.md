## My name is andinf Outcomer and please file below my submission

## Kubernetes, Docker, Containerisation and Virtualisation

1. Using google and/or Youtube research and report as to why Kubernetes has taken a prominent place in the computing infrastructure in most organization.
Kubernetes has become a very popular technology for managing containerized applications and has taken a prominent place in computing infrastructure in many organizations for several reasons:
1. Scalability: Kubernetes provides a highly scalable infrastructure for running and managing containerized applications. It can dynamically allocate resources to applications based on their needs and can easily scale up or down to meet changing demands.
2. Portability: Kubernetes is designed to be a portable platform that can run on any infrastructure, whether it be on-premises or in the cloud. This means that applications can be developed and deployed in a consistent manner across different environments, making it easier to manage and maintain them.
3. Resilience: Kubernetes provides a highly resilient infrastructure that can tolerate failures without impacting the availability of applications. It can automatically detect and recover from failures, ensuring that applications are always available to end-users.
4. Automation: Kubernetes provides a rich set of APIs and tools for automating the deployment, scaling, and management of containerized applications. This allows teams to focus on developing and delivering new features and functionality, rather than spending time on manual tasks.
5. Ecosystem: Kubernetes has a large and growing ecosystem of tools, plugins, and integrations that can be used to extend its functionality. This includes tools for monitoring, logging, and security, as well as integrations with other cloud services and platforms.
In summary, Kubernetes has become a popular choice for managing containerized applications because it provides a powerful and flexible infrastructure for deploying and managing modern cloud-native applications. Its scalability, portability, resilience, automation, and ecosystem have all contributed to its success and widespread adoption.


Docker, containers, and virtualization are all related concepts, but they are not interchangeable terms.
Docker is a popular platform that provides tools for building and managing containers. Docker allows developers to package their applications and dependencies into containers, which can be easily deployed and run on any machine that supports Docker. Docker also provides a registry for storing and sharing container images, making it easy to distribute and collaborate on containerized applications.
Containers, on the other hand, are a lightweight form of virtualization that allows applications to be packaged with their dependencies and run in a portable manner across different computing environments. Rather than creating a full virtual machine, containers use the host operating system and share the kernel with other containers on the same machine. This approach makes containers much more lightweight and efficient than virtual machines.
Virtualization is a technique used to create a virtual version of a computer system, including its hardware, operating system, and applications, that runs on top of a physical machine. A virtual machine (VM) is created by using a software layer called a hypervisor, which allows multiple VMs to run on a single physical machine.
Overall, Docker, Containers and virtualization are all important technologies for modern software development and deployment, with each one offering its own benefits and use cases. Virtualization is useful for running multiple operating systems on a single machine, while containers are ideal for packaging and deploying applications in a portable manner, and Docker provides a powerful platform for managing and deploying containerized applications.



## Linux administration and shell scripting

1. Research and report on the structure of Linux Filesystem
The Linux filesystem is organized as a hierarchical directory tree, with the root directory at the top of the tree. Each directory in the tree can contain files and subdirectories, and the entire filesystem can be accessed and manipulated through a variety of commands and utilities.

Here is a brief overview of the main directories and their contents in a typical Linux filesystem:

- /bin: Contains essential system binaries, such as the shell, ls, cp, and mv.

- /boot: Contains files required for booting the system, such as the kernel, bootloader, and configuration files.

- /dev: Contains device files, which allow access to hardware devices such as hard drives, keyboards, and mice.

- /etc: Contains system configuration files, such as those for network settings, user accounts, and startup scripts.

- /home: Contains user home directories, where users store their personal files and settings.

- /lib: Contains system libraries, which are shared code used by other programs.

- /media: Contains mount points for removable media, such as USB drives and CDs.

- /mnt: Contains mount points for filesystems that are mounted temporarily.

- /opt: Contains optional software packages that are not part of the base system.

- /proc: Provides a virtual filesystem that exposes information about the system and running processes.

- /root: The home directory of the root user.

- /run: Contains runtime data for system services.

- /sbin: Contains system binaries used for system administration tasks.

- /srv: Contains data for services provided by the system.

- /sys: Provides a virtual filesystem that exposes information about the system hardware.

- /tmp: Contains temporary files that can be deleted without harm.

- /usr: Contains user programs and libraries, such as compilers, text editors, and development tools.

- /var: Contains variable data that changes frequently, such as logs, spool files, and caches.

There may be additional directories or variations depending on the specific distribution and configuration.

Research of the most used flavor of Linux in the enterprise today

There are several popular flavors of Linux used in the enterprise today, but two of the most widely used are Red Hat Enterprise Linux (RHEL) and SUSE Linux Enterprise Server (SLES).

RHEL is a commercial Linux distribution developed by Red Hat and is widely used in enterprise environments. It is known for its stability, security, and scalability, and is often used for mission-critical applications and workloads. RHEL is available in both server and desktop editions, and it provides a robust set of tools for system management, security, and application development. RHEL also has a large ecosystem of third-party software vendors that provide enterprise-grade applications and services.

SLES is another commercial Linux distribution that is developed by SUSE, a German-based software company. SLES is also known for its stability and security, and it is often used for enterprise applications and workloads. SLES provides a range of features and tools for system management, virtualization, and high availability, and it has strong support for both physical and virtual environments. SUSE also has a large ecosystem of third-party software vendors that provide enterprise-grade applications and services.

Both RHEL and SLES are widely used in enterprise environments and are known for their reliability, security, and scalability. However, the choice of which flavor to use often depends on factors such as the specific needs of the organization, the existing IT infrastructure, and the preferences of the IT staff.





Describe what each of the following commands does.

1. `mkdir`: This command is used to create a new directory (folder) in the current working directory. For example, running `mkdir books` would create a directory called "books" in the current working directory.

2. `greg`: This is not a standard command in most operating systems or shells. It is possible that "greg" is an alias or user-defined function that performs a specific task.

3. `sudo`: This command is used to run a command with elevated privileges or permissions. It is often used to run commands as the root user or as another user with more permissions than the current user. For example, running `sudo apt-get update` would update the system's package repositories with elevated privileges.

4. `useradd`: This command is used to add a new user account to the system. It creates a new user with the specified username and assigns it a home directory and default settings.

5. `cat`: This command is used to display the contents of a file in the terminal. For example, running `cat myfile.txt` would display the contents of the file "myfile.txt" in the terminal.

6. `less`: This command is used to display the contents of a file in the terminal, but it allows the user to scroll through the contents of the file. For example, running `less myfile.txt` would display the contents of the file "myfile.txt" and allow the user to scroll up and down through the file.

7. `mv`: This command is used to move a file or directory from one location to another. It can also be used to rename a file or directory. For example, running `mv myfile.txt mytest/` would move the file "myfile.txt" to the directory "mytest".

8. `rm`: This command is used to remove a file or directory from the system. It is important to use this command with caution, as it will permanently delete the specified file or directory. For example, running `rm myfile.txt` would delete the file "myfile.txt" from the system.

9. `cd`: This command is used to change the current working directory in the terminal. For example, running `cd myfolder/` would change the current working directory to the directory "myfolder".

10. `ls` command is used to list the contents of a directory in the terminal. When you run the `ls` command without any arguments, it will display the names of all files and directories in the current working directory. 

Here's an example of how to use the `ls` command:
 Ls file1.txt file2.txt directory1 directory2

In this example, the `ls` command lists the contents of the current working directory, which includes two files (`file1.txt` and `file2.txt`) and two directories (`directory1` and `directory2`).

The `ls` command also supports a number of optional arguments that can be used to modify its behavior. For example:

- `ls -l`: This will display the contents of the directory in a long format, which includes additional information such as file sizes and permissions.
- `ls -a`: This will display all files and directories in the directory, including hidden files and directories (which are normally excluded from the output).

11. `pushed`: "Pushed" is not a command, but a past tense verb that could refer to the action of pushing changes to a Git repository using the `git push` command.

12. `pops`: "Pops" is not a command, but a noun or verb that could refer to a variety of things. It is not a standard command in most operating systems or shells.


## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

1. The following tools generally form part of a DevOps engineers toolbox. For each of these describe what it is used for and what class 
of products it forms part of.

1.Git is a distributed version control system that allows developers to track changes to their code and collaborate on code with others. Git is used to manage source code, track changes, and collaborate on code across a team or organization. Git is a command-line tool, but it can also be used with graphical user interfaces (GUIs) like GitKraken, SourceTree, or GitHub Desktop.

2. GitHub is a web-based hosting service for Git repositories that allows developers to store their code and collaborate with others. GitHub provides a range of features for managing code repositories, including pull requests, issue tracking, and code reviews. GitHub is also used as a platform for open-source projects, providing a way for developers to collaborate on code and share their work with others.

3. Visual Studio Code is a free, open-source code editor that provides a range of features for writing and debugging code. Visual Studio Code supports a wide range of programming languages and provides extensions and plugins that can be used to enhance its functionality. It is a popular tool among developers for its ease of use and powerful features.

4. AWS CLI is the command-line interface for Amazon Web Services (AWS), which is a cloud computing platform that provides a range of services for building and deploying applications. AWS CLI allows developers to interact with AWS services from the command line, making it easier to automate tasks and manage resources using scripts and other tools.

5. Terraform is a tool for building, changing, and versioning infrastructure as code. Terraform allows developers to define infrastructure resources using a high-level configuration language, and it can be used to manage resources across multiple cloud providers and on-premises infrastructure. Terraform is often used in conjunction with AWS CLI to automate infrastructure deployment and management on AWS.

6. Ansible is an open-source automation tool that allows you to automate the configuration, management, and deployment of software and infrastructure. It uses a simple and easy-to-read YAML-based language called Ansible Playbooks to define automation tasks. Ansible can manage multiple servers simultaneously, making it ideal for large-scale deployments. It can also integrate with other tools, such as Docker, AWS, and Azure, to provide a comprehensive automation solution.

7. Kubernetes, on the other hand, is an open-source container orchestration platform. It automates the deployment, scaling, and management of containerized applications. Kubernetes abstracts away the underlying infrastructure and provides a consistent API for deploying and managing applications. It allows you to easily scale your applications up or down based on demand, and provides advanced features such as load balancing, service discovery, and self-healing.

All the above tools are all essential tools for modern software development and deployment. Git and GitHub are used for version control and collaboration, Visual Studio Code is used for writing and debugging code, AWS CLI is used for interacting with cloud services, and Terraform is used for managing infrastructure as code. These tools together form a suite of products for building, deploying, and managing software applications. Ansible and Kubernetes can be used together to automate the deployment and management of containerized applications. Ansible can be used to provision the infrastructure needed to run Kubernetes, and then Kubernetes can be used to orchestrate the deployment and scaling of containerized applications. Ansible can also be used to automate the deployment of Kubernetes itself, making it easier to set up and maintain a Kubernetes cluster. Overall, Ansible and Kubernetes are powerful tools that can help streamline the DevOps workflow and improve the overall efficiency of infrastructure management.
With respect to Terraform, what is a provider?

Describe how Terraform manages state and what is the recommended approach to manage the state file?

Terraform is an infrastructure as code tool that allows you to define, provision, and manage infrastructure resources using code. One of the key features of Terraform is its ability to manage the state of your infrastructure.

Terraform uses a state file to keep track of the current state of your infrastructure. This state file is a JSON file that contains information about the resources that Terraform has created, modified, or deleted. The state file is used to determine what changes need to be made to your infrastructure when you apply your Terraform configuration.

The state file is essential to Terraform's functionality, as it allows Terraform to maintain an accurate picture of the infrastructure it's managing. Without the state file, Terraform would not be able to know which resources it created, or how to update or delete them when changes are made to the configuration.

To manage the state file, Terraform provides several options, including local state storage, remote state storage, and state locking. The recommended approach is to use remote state storage and state locking.

Remote state storage involves storing the state file in a remote location, such as an S3 bucket or a remote backend, instead of storing it locally on your machine. This approach provides several benefits, including improved collaboration, versioning, and backup and recovery.

State locking is a feature that prevents multiple users from modifying the state file at the same time, which could cause conflicts and corruption. State locking ensures that only one user can modify the state file at any given time, preventing conflicts and ensuring the integrity of the state file.

In summary, Terraform manages state by using a state file to keep track of the current state of your infrastructure. To manage the state file, it is recommended to use remote state storage and state locking to ensure the integrity and safety of the state file.


## System Architecture and Application Design, Cloud Computing (AWS)

1. Cloud Computing (AWS)
Cloud computing is the delivery of computing services, including servers, storage, databases, software, and more, over the internet, also known as the "cloud." Instead of having to buy and maintain physical computer hardware and software, you can use these services provided by a third-party provider, such as Amazon Web Services, Microsoft Azure, or Google Cloud Platform, on a pay-as-you-go basis. 
With cloud computing, you have access to a wide range of services and applications that can be quickly provisioned and deployed, as well as scaled up or down as needed, without the need to invest in and manage complex IT infrastructure. This can help businesses and individuals save money, increase efficiency, and focus on their core competencies instead of worrying about IT infrastructure. 
Some common examples of cloud computing include using web-based email services like Gmail or Microsoft Outlook, storing and sharing files on cloud storage services like Google Drive or Dropbox, or running applications and hosting websites on cloud-based servers.
You have configured your AWSCLI command line tool with the keys of a user you have created in your AWS account. Upon running the AWSCLI it complains of a permissions problem. What would you do to fix the problem?
If the AWS CLI is complaining of a permissions problem, it could be due to a number of different issues. Here are some steps you can take to troubleshoot the problem:
1. Check the user's permissions: Make sure that the user you created in your AWS account has the appropriate permissions to perform the actions you are trying to execute with the AWS CLI. You can check the user's permissions by reviewing the user's IAM policy in the AWS Management Console.
2. Check the AWS CLI configuration: Make sure that the AWS CLI is configured correctly with the user's access key ID and secret access key. You can double-check this by running the "aws configure" command and verifying that the keys are correct.
3. Check the AWS CLI version: Make sure that you are using the latest version of the AWS CLI, as older versions may have compatibility issues with certain AWS services.
4. Check the AWS service status: Check the AWS Service Health Dashboard to see if there are any known issues with the AWS service you are trying to use. 
5. Check the error message: Review the error message generated by the AWS CLI to see if it provides any additional information on what the problem might be. This can help you narrow down the issue and find a solution.
If none of these steps resolve the issue, you may need to seek additional help from AWS support or other technical resources.




AWS has data centres aggregated in places called regions. Name three regions closest to your home.
AWS data centers, also known as Availability Zones, close to me in the East Coast of the USA are:
1. US East (N. Virginia) - located in Northern Virginia, this is the largest and oldest AWS region, and it offers a wide range of services and features.
2. US East (Ohio) - located in Ohio, this region was launched in 2016 and offers lower latency and better resilience for customers located in the Midwest.
3. AWS GovCloud (US-East) - located in the same Northern Virginia area as the US East (N. Virginia) region, this region is designed to meet the specific regulatory and compliance requirements of government agencies and contractors.

Describe how the AWS root account is different from ordinary IAM user and what is the recommended approach to handle the details of the AWS root account?
The AWS root account is the initial account created when you sign up for an AWS account. It has full access to all AWS services and resources, and can perform any action within your AWS account, including managing IAM users and policies, creating and deleting resources, and accessing billing information. Because of this, the root account has the highest level of permissions within your AWS account and should be treated with caution.
On the other hand, an IAM user is a separate identity within your AWS account that has its own set of permissions and access keys. You can create IAM users with specific permissions to access and manage AWS resources, without giving them full access to your AWS account. IAM users can also be used to enforce the principle of least privilege, which means granting only the minimum permissions necessary to perform a specific task.
It is recommended to secure the root account by enabling multi-factor authentication (MFA) and creating an IAM user with administrative permissions. This IAM user can be used to perform administrative tasks within your AWS account, while the root account should be used only for emergency situations or to perform tasks that require full access to your AWS account. By using an IAM user with administrative permissions, you can reduce the risk of accidental or intentional misuse of your AWS resources and services.
In addition to securing the root account through the use of an IAM user with administrative permissions, it is recommended to follow the principle of least privilege when creating additional IAM users and roles. This means granting only the minimum permissions necessary to perform a specific task or access a specific resource, and regularly reviewing and updating permissions as necessary.

What are the AWS access key and secret access key used for?
The AWS access key and secret key are used for programmatic access to AWS services through APIs, SDKs, and command-line tools. When you create an IAM user, AWS generates an access key ID and a secret access key for that user. The access key ID is a unique identifier that AWS uses to identify the IAM user, and the secret access key is a secret string of characters that is used to authenticate the IAM user when making API requests to AWS services.

The access key and secret key are used together to sign API requests to AWS services, providing a secure way to authenticate programmatic access to your AWS resources. When you make an API request to an AWS service, you include your access key ID and a signature based on your secret access key in the request. The AWS service then verifies the signature to ensure that the request is coming from a trusted source and that the IAM user making the request has the necessary permissions to perform the requested action.

It is important to keep the access key and secret key secure, as they provide full programmatic access to your AWS resources. You should never share your access key and secret key with anyone who does not need access to your AWS resources, and you should rotate your access keys regularly to help secure your AWS account. Additionally, you should always use secure methods to store and transmit your access keys, such as using AWS Key Management Service (KMS) to encrypt your access keys at rest and using HTTPS when transmitting your access keys over the internet.




## Site Reliability Engineering (SRE), Troubleshooting, Observability

1. To what extend do you use public resources such as Google and Youtube to aid in your problem resolution endeavour?
I use google and youtube daily to help me find answers to my questions
What would be your attitude if your manager asked you to use Google to investigate a critical issue in your infrastructure?
I will use google as well as Youtube and books to investigate critical issue in my infrastructure.



## DevOps and Agile Transformation principles and methodology
What behavioral attitudes are conducive for the fostering of Agile and DevOps ways of working?
Agile and DevOps ways of working require a specific set of behavioral attitudes that help foster collaboration, communication, and continuous improvement. Here are some of the key attitudes that are conducive to fostering agile and DevOps ways of working:
1. Openness: Being open to new ideas, feedback, and perspectives is critical for agile and DevOps teams. This means being receptive to new ways of doing things, as well as being willing to share your own ideas and insights.
2. Collaboration: Agile and DevOps teams rely on collaboration to get work done effectively. This means working closely with other team members, sharing information and knowledge, and working towards shared goals.
3. Flexibility: Agile and DevOps require the ability to adapt to changing requirements and priorities. Being flexible means being able to pivot and adjust as needed, without losing focus or momentum.
4. Continuous improvement: Agile and DevOps teams are always looking for ways to improve their processes and practices. This means being willing to experiment, learn from failures, and iterate on what works.
5. Accountability: Agile and DevOps teams hold themselves and each other accountable for delivering high-quality work and meeting commitments. This means taking ownership of your work, communicating effectively, and following through on your commitments.
6. Empathy: Agile and DevOps teams rely on empathy to understand the needs and perspectives of stakeholders and customers. This means being able to put yourself in someone else's shoes and view things from their perspective.
7. Trust: Agile and DevOps teams rely on trust to work effectively together. This means trusting your team members to deliver on their commitments, sharing information freely, and being transparent about progress and challenges.
What steps do you personally take to promote collaboration and communication in your team
Promoting collaboration and communication in a team is essential for achieving success. Here are  steps that I take to promote collaboration and communication in my team:

1. Set clear goals and expectations: Ensure that everyone on the team understands the goals and expectations for the project. Make sure that the goals are specific, measurable, achievable, relevant, and time-bound (SMART).

2. Foster a culture of open communication: Encourage team members to share their thoughts, ideas, and concerns openly. Create an environment where everyone feels comfortable speaking up and sharing their opinions.

3. Use collaboration tools: Use collaboration tools such as Slack, Microsoft Teams, or Trello to help team members communicate and collaborate effectively. I use these tools to share information, assign tasks, and track progress.

4. Schedule regular team meetings: Schedule regular meetings to discuss project progress, address issues, and brainstorm new ideas. These meetings are inclusive and I encourage everyone to participate.

5. Encourage feedback: Encourage team members to provide feedback to each other on their work, ideas, and communication. Provide constructive feedback and encourage everyone to do the same.

6. Assign team roles and responsibilities: Assign specific roles and responsibilities to each team member based on their skills and expertise. This will help ensure that everyone is clear on their responsibilities and that tasks are completed efficiently.

7. Celebrate successes: Celebrate team successes and milestones to boost morale and encourage collaboration. Recognize individual contributions and show appreciation for everyone's hard work.

All these steps, help to promote collaboration and communication in my team, which lead to improved performance, increased productivity, and better outcomes.
