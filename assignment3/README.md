## Kubernetes, Docker, Containerisation and Virtualisation
A hypervisor is software that enables multiple instances of operating systems to run on the same physical computing resources.
Hypervisors
The hypervisor, or VMM, is the software layer that sits underneath the guest operating system allowing it to believe there is really hardware in place
 The container runtime is the software installed on a host system that allows it to isolate its resources for containers, pull down container.these tools make it easier to securely execute and efficiently deploy containers, and are a key component of container management


## Linux administration and shell scripting

mkdir -p Sports/ft/af/pwdkumba
tree Sports
Grep is an essential Linux and Unix command. It is used to search text and strings in a given file.
The sed command, short for stream editor, performs editing operations on text coming from standard input or a file
The Awk is a powerful scripting language used for text scripting. It searches and replaces the texts and sorts, validates, and indexes the database


## CICD, Git, GitHub, GitHub Action, Infrastructure as as Code (IaC), Terraform, Packer and Ansible
1. You create a repository in GitHub called <b>myfirstrepo</b>. You then clone this repository on your local laptop. On your laptop how would you check its remote address? How would you go about changing the remote address so that it points to repository called <b>mysecondrepo</b>?


After cloning,use git remote -v to check and make sure it pointing towards to my firstrepo,to change the remote address,you will need to delete the .git folder and reinitialise git(git init),then (git remote add (UrL of my second repo) 



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



## System Architecture and Application Design, Cloud Computing (AWS)
1. You have worked thus far with systems that you have had to download and install on your local laptop as well as systems hosted remotely on some external cloud. Describe in details the features and capabilities of all the systems (local and remote) that you have worked with thus far on this training. Draw a solution architecture diagram depicting these systems and where they fit in your solution landscape.
2. For all the systems that you have installed locally, write a manual for its installation and configuration.



## Site Reliability Engineering (SRE), Troubleshooting, Observability

Application performance monitoring (APM) is the practice of tracking key software application performance metrics using monitoring software and telemetry data. Practitioners use APM to ensure system availability, optimize service performance and response times, and improve user experiences

 Metrics represent the raw measurements of resource usage or behavior that can be observed and collected throughout your systems.
Metrics are useful because they provide insight into the behavior and health of your systems, especially when analyzed in aggregate. They represent the raw material used by your monitoring system to build a holistic view of your environment, automate responses to changes, and alert human beings when required. Metrics are the basic values used to understand historic trends, correlate diverse factors, and measure changes in your performance, consumption, or error rates

System Log (syslog): a record of operating system events. It includes startup messages, system changes, unexpected shutdowns, errors and warnings, and other important processes. Windows, Linux, and macOS all generate syslogs

Log files are important as they store valuable information which can be used to recreate past events, find security flaws, or troubleshoot




## DevOps and Agile Transformation principles and methodology
Increased communication and collaboration in an organization is one of the key cultural aspects of DevOps. The use of DevOps tooling and automation of the software delivery process establishes collaboration by physically bringing together the workflows and responsibilities of development and operations. Building on top of that, these teams set strong cultural norms around information sharing and facilitating communication through the use of chat applications, issue or project tracking systems, and wikis. This helps speed up communication across developers, operations, and even other teams like marketing or sales, allowing all parts of the organization to align more closely on goals and projects.

The DevOps model relies on effective tooling to help teams rapidly and reliably deploy and innovate for their customers. These tools automate manual tasks, help teams manage complex environments at scale.


DevOps, we see that making work visible is right at the top of the first way, meaning it is a prerequisite for DevOps. Without having visibility, it is impossible to effectively identify bottlenecks and act upon them. 

Three Ways of DevOps:

1)     The First Way – FLOW

Make work visible
Limit hand-offs
Left to right
Small batch sizes
Limit WIP
Prepare and sync environments: DEV, QA, Pre-Prod, Prod
CI/CD automation
2)     The Second Way - FEEDBACK

Fast feedback right to left
Fast feedback across the value stream
Recovery
3)  The Third Way – RELENTNESS IMPROVEMENT

Continuous experimentation
Risk taking and learning
Relentless improvement 
Signals that we have a high level of transparency on our Kanban board is reflected as the following:

-         It is clear what the tasks team members are working on and what the complexity of the tasks is.

-         Priority and work in progress (WIP) limits are defined and respected.

-         It is clear from the board what is the bottleneck for flow. We can therefore protect our 'critical constraint'.

-         Blocked items are clearly indicated.

-         Dependencies are indicated.



New commands logs - Enter up to ten new commands you have learnt this week

git config	Setup user information
git init	Initialize a repository as a Git repository
git clone [url]	Clone a local repository from Github
git add [file path]	Add file or folder to your commit staging
git commit -m “[message]”	Commit staged content
git push [alias] [branch]	Push commit to Github
git fetch [remote] [branch]	Download commits, files, and refs from remote to local repo
git remote add [name] [url]	Modify a repository ./.git/config file
git branch [branch]	Create, list, rename, and delete branches


Glossary of the week - Enter new technical words you have learnt this week and their meanings.

Glossary of the week - Enter new technical words you have learnt this week and their meanings.
1 application programming monitoring

2.container runtime
3.hypervisor
4.Packer 
5.Ansible
6.GitHub Action
7.system metric
8.system log
9.
