## Kubernetes, Docker, Containerisation and Virtualisation

1. What is a hypervisor and where does it sit in the server virtualisation stack?
   A hypervisor is a software or firmware layer that enables server virtualization. It sits directly on top of the server hardware and is responsible for managing the virtual machines (VMs) that run on the server. There are two main types of hypervisors: Type 1 (bare-metal) hypervisors run directly on the server hardware, while Type 2 (hosted) hypervisors run as software on top of an existing operating system.

2. What is a container runtime and name the two most common runtimes?
   A container runtime is a software component that manages the execution of containers. It provides the necessary environment and tools to run and manage containerized applications. The container runtime is responsible for starting, stopping, and monitoring containers, as well as handling their resource allocation and isolation.
    The two most common container runtimes are: Docker and containerd


## Linux administration and shell scripting
1. Use just one command to create a directory structure where the directory sports contains a directory called footballteams which itself contains africanteam which itself contains pwdkumba.
  $mkdir -p sports/footballteams/Africanteam/pwdkumba

2. Use the tree command to display your directory structure.
  tree sports
3. Research the following linux commands
    a) grep
      It is a command-line utility used for searching and filtering text based on patterns or regular expressions.

    b) sed
      It is a stream editor used for manipulating and transforming text, often used for search-and-replace operations or text modifications.

    c) awk
      It is a versatile text processing tool used for extracting and manipulating data within structured text files, commonly used for data extraction, filtering, and reporting.
    
            
## CICD, Git, GitHub, GitHub Action, Infrastructure as as Code (IaC), Terraform, Packer and Ansible
1. You create a repository in GitHub called <b>myfirstrepo</b>. You then clone this repository on your local laptop. On your laptop how would you check its remote address? How would you go about changing the remote address so that it points to repository called <b>mysecondrepo</b>?
 After cloning, you can check by using the command (git remote -v) to make sure its pointing to myfirstrepo. 
    To change the remote address, you will need to delete the .git folder present in myfirstrepo and reinitialise git (git init) then (git remote add #mysecondrepo). 
    Alternative, you can use the command (git remote set-url origin <new_remote_url>)

2. You have a workflow running on GitHub Action that has the following code;
```
jobs:
  deploy_to_production:
    runs-on: ubuntu-latest
    name: deploy to production with soruce code
    steps:
      - name: Checkout GitHub Action
        uses: actions/checkout@v2

      - name: Login via Azure CLI
        uses: azure/login@v1
        with:
          creds: ${{ secrets.AZURE_CREDENTIALS }}

      - name: deploy to production step with soruce code
        uses: azure/spring-cloud-deploy@v1
        with:
          azure-subscription: ${{ env.AZURE_SUBSCRIPTION }}
          action: deploy
          service-name: <service instance name>
          app-name: <app name>
          use-staging-deployment: false
          package: ${{ env.ASC_PACKAGE_PATH }}
```
Describe what you think this code is doing.
  The given code represents a GitHub Actions workflow for deploying a Spring Cloud application to production using Azure services. Here's a breakdown of the workflow steps:

The Checkout GitHub Action step uses the actions/checkout@v2 action to fetch the source code from the repository.

The Login via Azure CLI step uses the azure/login@v1 action to authenticate with Azure using the credentials stored in the AZURE_CREDENTIALS secret.

The deploy to production step with source code step uses the azure/spring-cloud-deploy@v1 action to deploy the application to production. It requires the following inputs:

azure-subscription: The Azure subscription ID.
action: The deployment action to perform, which is deploy in this case.
service-name: The name of the Spring Cloud service instance.
app-name: The name of the application.
use-staging-deployment: A boolean value indicating whether to use staging deployment (set to false).
package: The path to the package (JAR, ZIP, or folder) containing the application code, specified using the ASCP_PACKAGE_PATH environment variable.


## System Architecture and Application Design, Cloud Computing (AWS)
1. You have worked thus far with systems that you have had to download and install on your local laptop as well as systems hosted remotely on some external cloud. Describe in details the features and capabilities of all the systems (local and remote) that you have worked with thus far on this training. Draw a solution architecture diagram depicting these systems and where they fit in your solution landscape.
2. For all the systems that you have installed locally, write a manual for its installation and configuration.
3. In a general manner describe would you would interact with AWS account
4. AWS provide a public and a private area in which you could deploy your services. In which of these would you deploy the following services?
    a) EC2 instances
    b) DynamoDB databases
    c) VPC network
    d) S3 buckets
    e) IAM users


## Site Reliability Engineering (SRE), Troubleshooting, Observability

1. Research on what APM (application programming monitoring)
2. What is a system metric and why might it be useful to collect metrics?
3. What is an system log and why might you want to collect logs?


## DevOps and Agile Transformation principles and methodology

1. Communication, Collaboration and Automation and key aspects of a successful DevOps implementation. Describe why these traits are important in a DevOps transformation process.
2. You work for an organisation that is very keen to <b> make their work visible</b> across the organisation. What do you understand by this and how would you suggest they go about it?


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

