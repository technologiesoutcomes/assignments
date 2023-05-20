## My name is Stella nchang Outcomer and please find below my submission done in collaboration with Esther Dagiloke
## Kubernetes, Docker, Containerisation and Virtualisation
1. VMs and Containers emulate entire computer systems including the hardware by running a hypervisor. The benefit of these two categories of tools for working with images, is that they run on top of the hypervisor and can only see the virtualized hardware, staying isolated from the host machine and other VMs, and run the same in any environment.  Running separate OS for each VM incurs a lot of CPU and memory usage, and this a drawback in itself. With Containers, there is less security compared to VMs despite isolation.

2. What is a docker image and how are they created?
Docker image is a server templating tool that is used to capture an OS, Sofware, files, and all relevant details; then use other Iac tools like Ansible to install that image on other servers

3. What is a docker container and how do u run it? 

Docker container is a software platform that enables us to build, test and deploy applications faster. Docker packages Software into standardized units called container. Kubernetes allows you to define how to manage Docker containers as code. To run this, you first deploy a kubernetes cluster, which is a group of servers used to run Docker containers. Most cloud providers have support for deploying managed kubernetes clusters such as: EKS, GKE, AK
## Linux administration and shell scripting

1. XXXX

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

a. What do you understand by the term Impotence? 

Idempotence is a function that can be executed several times without changing its behavior or result beyond its first iteration. Terraform code and most Ansible functions are idempotence by default 
b. Benefits of adopting DevOps way of working 

The main goal of DevOps is to automate as much of Sofware delivery process, making it more efficient, secure, dependable and compliant 

Using DevOps an organization can manage almost all their infrastructure in code (servers, databases, networks, documentation, application configuration, automation tests, deployment processes and much more)          

DevOps way of working is cost effective, as organizations don’t have to invest heavily on hardware equipment like servers, but can rent scalable cloud space as needed. 

c.  Some provisioning and configuration management tools require the installation of agents on managed servers. Can you list the advantages and disadvantages of tools based on agents? 

Terraform, Ansible, ClouFormation, Heat, and Pulumi are agentless since agents are already installed as part of the infrastructure.  Terraform deploys servers with an AMI that has the agent already installed, which will take care of business. Providers like AWS, AZURE, GOOGLE CLOUD and others take care of installing, managing and authenticating agent software on each of their physical servers. 

Some CMT (Chef Puppet) require installation of agent software which runs in the background on each server that needs to deploy, and this agent is responsible for installing the latest configuration management updates. The downside of agents involves bootstrapping, maintenance, security; figuring how to authenticate the agent to server communication by opening surface areas to attackers, failures in infrastructure. 

d. Compare and contrast mutable and immutable infrastructures design paradigms. 

CMT such as Puppet, Chef and Ansible typically default to mutable infrastructure, while provisioning tools like Terraform are immutable. 

With mutable infrastructure code, it is possible to modify its internal state after creation. For example, if you instruct Chef to install a new version of software, it will run updates on existing servers, and changes will happen in place. Overtime it builds a history of changes and each server becomes slightly different   than others, leading to configuration bugs that might prove difficult to diagnose and fix.  
Immutable infrastructure on the other hand, is a simpler, consistent, reliable and predictable deployment process; you can’t change the object’s state after creation. Using provisioning tool to such as Terraform to deploy machine images created by Docker or Packer, most changes are deployments of a completely new set of servers and terminates the old ones, avoiding bug drifts. 

e. Name some commercial and enterprise tools and the circumstances under which you will would recommend them 

Configuration Management Tools (CMT) 

Ansible, Chef and Puppet are tools design to install and manage software on existing servers. Ansible, for example, enforces a coding convention that is consistent, has predictable structure, including documentation, file layout named parameters, secrets management and many more. Most functions of these CMT tools are idempotent by default and are design to manage large numbers remote servers. CMT would be a good fit for businesses that possess or manage a huge number of servers. 

Server Templating Tools (STT) 

Docker, Packer, and Vagrant etc. are alternative to CMT and enable you to create an image of a server that captures a fully self-contained snapshot of the OS, Sofware, files, and all relevant details. You can then use other Iac tools like Ansible to install that image on other servers. Two main categories of tool for working with images: VMs and Containers. These can be recommended for an organization that 

Orchestration Tools (OT) 
Tools such as Kubernetes, Amazon ECS, Docker Swarm etc.     Used to deploy VMs and containers, roll out updates to existing fleet of VMs and Containers using strategies such rolling deployment, blue-green deployment and canary deployment. Monitor the health of VMs and Containers, auto scaling, load balancing and service discovery. 

Provisioning Tools 
While CMT, STT, AND OT define code that runs each server, provisioning tools such as Terraform, Cloud Formation, OpenStack Heat and Pulumi  creates the servers, databases, caches, load balancers, ques, subnet configurations firewall routing rules, Secure Sockets Layers (SSL) certificates and other aspects of infrastructure. 
## System Architecture and Application Design, Cloud Computing (AWS)

1. XXXX


## Site Reliability Engineering (SRE), Troubleshooting, Observability

1. XXXX


## DevOps and Agile Transformation principles and methodology

1. XXXX

2. XXXX

3. XXXX

4. XXXX


## New commands logs - Enter up to ten new commands you have learnt this week

| Number      | Commands | What does it do and how might you check its effect     |
| :---        |    :----:   | :---  |
| 1  | Ls [a-h] * | List all files in the current directory that start with letters ‘a’ through ‘h’   |
| 2  | Whatis[command] | Used to display the first or las line few lines of a file respectively   |
| 3  | Ctrl+w | Delete the word immediately before the cursor   |
| 4  | ‘Ctrl+B’ and ‘Ctrl+F’ | Move the cursor back one word / Move the cursor forward one word   |
| 5  | chmod        | Used to modify file permission   |
| 6  | Ctrl+Z       | Stop a process and return to shell   |
| 7  | “/dev/null”  | dispose of unwanted output from a command ex: ls  > /dev/null   |
| 8  | XXXXXXXX       | YYYYYYYY   |
| 9  | XXXXXXXX       | YYYYYYYY   |
| 10 | XXXXXXXX       | YYYYYYYY   |

## Glossary of the week - Enter new technical words you have learnt this week and their meanings.

| Number   | Word | Meaning     |
| :---     | :----:   |  :---  |
| 1  | Serial in the play book | Parameter used in Ansible for a rolling deployment to update servers in batches   |
| 2  | hypervisor | Used to simulate or virtualize the underlying CPU, memory, hard drive, and networking ex: VMware, Virtual box   |
| 3  | kernel space & user space | Code running on kernel space has unrestricted access to all hardware, and no security restrictions.  Code running in user space doesn’t have direct access to hardware and must use APIs exposed by the OS kernel instead. APIs enforce security restrictions and safety such as: user permissions; a crash in user space App affects only that App, so all code runs in user space.  |
| 4  | Rolling, blue-green, and canary deployment | YYYYYYYY   |
| 5  | pod |One or more Docker container   |
| 6  | Secure Sockets Layers SSL | A protocol that provides secure communication over internet – server and client authentication |
| 7  | Bug drifts        | Occurs when an app microservice or infrastructure drifts out of its intended configuration or operational boundaries  |
| 8  | XXXXXXXX       | YYYYYYYY   |
| 9  | XXXXXXXX       | YYYYYYYY   |
| 10 | XXXXXXXX       | YYYYYYYY   |

