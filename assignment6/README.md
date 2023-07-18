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

1.  What is a Kubernetes ingress and what role does it serve?

2.  What is a service in Kubernetes?


## Linux administration and shell scripting

1. Research the concept of heredoc in shell scripting. Use this site as a resource - https://stackoverflow.com/questions/2953081/how-can-i-write-a-heredoc-to-a-file-in-bash-script
2. Write a bash shell script which when run will create a file called <b>myconfig.conf</b> with the following as content of the file.
```
name=outcomer
town=mytown
class=seven
gender=male
```
3. Write a bash script which will take a single argument and which when run will create a file called <b>myconfigparams.conf</b> with the following as content of the file. The argument should substitute the placeholder ????? below
```
name=?????
town=mytown
class=seven
gender=male
```

4. The following scripts is used as part of user data in an EC2 instance provisioning. Analyse the script and explain what it is doing?
```
#!/bin/bash -xe
     sudo apt-get update -y # good practice to update existing packages
     sudo apt-get install -y awscli
     sudo apt install -y jq 
     sudo mkdir /etc/ssl/nginx
     # install the key and secret 
     aws secretsmanager get-secret-value --secret-id nginxcert --region ${AWS::Region} | jq --raw-output '.SecretString'| tr -d '"{}' | sudo tee /etc/ssl/nginx/nginx-repo.crt
     aws secretsmanager get-secret-value --secret-id nginxkey --region ${AWS::Region} | jq --raw-output '.SecretString'| tr -d '"{}' | sudo tee /etc/ssl/nginx/nginx-repo.key
     # Add the repo
     sudo wget https://cs.nginx.com/static/keys/nginx_signing.key && sudo apt-key add nginx_signing.key 
     sudo wget https://cs.nginx.com/static/keys/app-protect-security-updates.key && sudo apt-key add app-protect-security-updates.key
     sudo apt-get install -y apt-transport-https lsb-release ca-certificates
     printf "deb https://pkgs.nginx.com/plus/ubuntu `lsb_release -cs` nginx-plus\n" | sudo tee /etc/apt/sources.list.d/nginx-plus.list
     sudo wget -P /etc/apt/apt.conf.d https://cs.nginx.com/static/files/90pkgs-nginx
     # Install and start 
     sudo apt-get update -y # good practice to update existing packages
     sudo apt-get install nginx-plus -y # install web server   
     sudo systemctl start nginx.service # start webserver
```

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

1. Write the definition of an EC2 resource in Terraform specifying the following as part of the user data.
```
#!/bin/bash
yum update -y
amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
yum install -y httpd mariadb-server
systemctl start httpd
systemctl enable httpd
usermod -a -G apache ec2-user
chown -R ec2-user:apache /var/www
chmod 2775 /var/www
find /var/www -type d -exec chmod 2775 {} \;
find /var/www -type f -exec chmod 0664 {} \;
echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php
```
2. Launch an EC2 instance and manually run the following scripts to install Jenkins. Also run post installation checks to ensure all is running well.
From (https://phoenixnap.com/kb/install-jenkins-ubuntu)
```
#!/bin/bash
sudo apt update
sudo apt install openjdk-11-jdk -y
sudo apt install maven -y

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update
sudo apt install jenkins -y
sudo systemctl status jenkins
sudo systemctl enable --now jenkins
sudo ufw enable
sudo ufw allow 8080
sudo ufw status
```


## System Architecture and Application Design, Cloud Computing (AWS)

1. You have recently joined an organisation and your boss asked your to review centralised Identity and Key management systems with a view to centralising 
the management of SSH keys. She suggests that you look into FreeIPA, LDAP, Active Directory. Research these products and describe how they might solve your problems.

2. We want to launch an EC2 instance that will host a website and we want to complete the installation and configuration of the website after the provisioning of the EC2 instance user user data and the shell script below. Launch an EC2 instance using using an AWS Linux 2 Kernel 5.10 AMI and using the script below complete the exercise, including post implementation checks to ensure all went well.
```
#!/bin/bash
yum update -y
amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
yum install -y httpd mariadb-server
systemctl start httpd
systemctl enable httpd
usermod -a -G apache ec2-user
chown -R ec2-user:apache /var/www
chmod 2775 /var/www
find /var/www -type d -exec chmod 2775 {} \;
find /var/www -type f -exec chmod 0664 {} \;
echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php
```

Some useful Post implementation checks

```
SSH onto the server and perform the following;
Logs 
less /var/log/cloud-init-output.log

Check user data entry:
curl -sL http://169.254.169.254/latest/user-data

View the AMI details
cat /etc/image-id

Check running processes on the server
ps -ef | grep ssm

ps -ef | grep apache

ps -ef | grep php

systemctl --type=service --state=running

systemctl list-units --type=service

systemctl list-units --type=service --state=active

systemctl status sshd

on the browser go to the website
http://<IP>:80
```

3. Install and configure the MERN stack using the material in this link https://www.linode.com/docs/guides/how-to-create-a-mern-stack-application/


4. You are implementing the design of two systems that are supposed to talk to each other. Come up with five questions that will help you better understand how these systems integrate with each other, that is the <b> the connective tissues </b>.


5. When building a Three-tier architecture involving a Load balancer and an Auto-Scaling Group what steps would you take to ensure that there is a <b>connective tissue </b> between these two components? Refer to this document - https://docs.aws.amazon.com/autoscaling/ec2/userguide/attach-load-balancer-asg.html

6. At what level of the network OSI or TCP/IP stack does the following devices operate?

* Switches
* Routers
* AWS Application Load Balancer
* AWS Network Load Balancer

7. With respect to network communication define what these terms mean.
* Encapsulation
* De-encapsulation
* Packets
* Payload
* Headers
* Trailers


8. Why is a device operating at layer 4 of the OSI model more performant than one operating at layer 7?


9. What roles does the Instance Metadata Service (IMDS) play in the architecture of the EC2 service?


10. What are the various methods for connecting to an EC2 instance and could you list their advantages and disadvantages.
Review the following links to learn more

* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connect.html
* https://aws.amazon.com/blogs/infrastructure-and-automation/securing-your-bastion-hosts-with-amazon-ec2-instance-connect/
* https://aws.amazon.com/blogs/infrastructure-and-automation/toward-a-bastion-less-world/

11. What roles does an Auto-Scaling Group (ASG) play in an application serving architecture?


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

