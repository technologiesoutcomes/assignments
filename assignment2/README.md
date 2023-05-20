# Assignment 2

Complete this assigment preferably as a team and submit on or before 19/05/2023. If you work as a team provide the names of all the individuals of the team.


## Kubernetes, Docker, Containerisation and Virtualisation

1. Containers and Virtual machines are two approaches to deploying applications. Name the advantages and disadvantages of each.

2. What is a Docker image and how are they created?

3. What is a Docker container and how might you run them?

## Linux administration and shell scripting

1. Write a shell script that takes a single input arguments and echoes it back when it is run.

2. Write a shell script that creates a directory call "sports" and inside the "sports" directory create two other subdirectories called "football" and "handball". You should be able to run the script multiple times without it failing.

3. Copy the code below into a file called hello.sh and run it. Explain the behaviour.
```
#!/bin/bash
echo "You are using $(basename $0)"
for n in $*
do
    echo "Hello $n"
done
exit 0
```
4. Copy the script below into a file called addme.sh and analyse it line by line. Run it and describe in details the behavior.

```
#!/bin/bash
# (@)/ph
# A very simple telephone list
# Type "ph new name number" to add to the list, or
# just type "ph name" to get a phone number
PHONELIST=~/.phonelist.txt
# If no command line parameters ($#), there
# is a problem, so ask what they're talking about.
if [ $# -lt 1 ] ; then
    echo "Whose phone number did you want? "
    exit 1
fi
# Did you want to add a new phone number?
if [ $1 = "new" ] ; then
shift
    echo $* >> $PHONELIST
    echo $* added to database
exit 0
fi
# Nope. But does the file have anything in it yet?
# This might be our first time using it, after all.
if [ ! -s $PHONELIST ] ; then
    echo "No names in the phone list yet! "
    exit 1
else
    grep -i -q "$*" $PHONELIST # Quietly search the file
    if [ $? -ne 0 ] ; then # Did we find anything?
        echo "Sorry, that name was not found in the phone list"
        exit 1
    else
        grep -i "$*" $PHONELIST
    fi
fi
exit 0
```
5. Create a script that reads in three positional parameters from the command line,
assigns those parameters to variables names ONE, TWO, and THREE, respectively,
and then outputs that information in the following format:
There are X parameters that include Y. The first is A, the second is B, the third is C.
Replace X with the number of parameters and Y with all parameters entered.
Then replace A with the contents of variable ONE, B with variable TWO, and C
with variable THREE.

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

1. Read Chapter 1, page 1 - page 37 of the Terraform Up and Running book and with respect to your learning answer the following questions:

* What do you understand by the term Idempotence?

* What are the benefits of adopting a DevOps way of working for an organisation?

* What are the benefits of provisioning infrastructure using tools like Terraform and Ansible?

* Some provisioning and configuration management tools require the installation of agents on managed servers. Can you list the advantages and disadvantages of tools based on agents?

* Compare and contrast mutable and immutable infrastructures design paradigms.

* Name some commercial and enterprise tools and the circumstances under which you would recommend them.

* What do you understand by imperative and declarative way of provisioning infrastructure?

2. Describe the role that GitHub Actions plays in a fully automated CICD integrated toolchain?

3. What is a Runner in the context of a provisioning pipeline?

4. What GitHub Action code syntax would you implement to trigger a GitHub Action workflow upon a pull request on a codebase?

5. In the context of GitHub Actions, what are actions and where might you obtain them?


## System Architecture and Application Design, Cloud Computing (AWS)

1. Draw a solution architecture diagram illustrating the flow of information in a provisioning pipeline comprising AWS, GitHub, your laptop, Terraform and Terraform state file stored in AWS.
2. You run a command on your local laptop to clone a public repository and then run another command to push the cloned repository to your own GitHub repository. Draw a solution architecture diagram to depict the flow of information.


## Site Reliability Engineering (SRE), Troubleshooting, Observability

1. You are asked by your manager to implement an automated system to collect metrics from your infrastructure by using a third party vendor's product. What steps might you take to ensure the system is not going to cause unwanted effects?  How might you check that?
2. Your manager asked you to run a script that is unfamiliar to you. How are you going to go about ensuring that this operation is done safely?


## DevOps and Agile Transformation principles and methodology

1. Read the blog article given in Reference 1 (Become A DevOps Engineer in 2023: A Comprehensive Guide) and answer the following question. According to the author, what are the key technologies, tools and systems an aspiring DevOps should learn?

2. Read the blog article given in Reference 4 "How to find Remote DevOps Full time Gigs". To what extend do you agree or disagree with the main argument of the article?

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


## Reference

1. Become A DevOps Engineer in 2023: A Comprehensive Guide
https://blog.brainboard.co/become-a-devops-engineer-in-2023-a-comprehensive-guide-db3f614e4051

2. Terraform Up and Running.

3. Kubernetes Patterns

4. How to find Remote DevOps Full time Gigs https://sharonsahadevan.medium.com/learn-how-i-found-remote-devops-jobs-from-my-perspective-382c15514cd5

