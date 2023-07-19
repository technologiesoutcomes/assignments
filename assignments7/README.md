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

1.  

2.  


## Linux administration and shell scripting

1

2

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

1. Your provisioning architecture has been partitioned into two tiers - a base network infrastructure tier and an application tier - each of which is provisioined using Terraform and has its own state file. Describe how you could dynamically retrieve parameters that are held in the base network tier state file from within the application tier Terraform definitions.
## To dynamically retrieve parameters from the base network tier state file in the application tier Terraform definitions, you can use the Terraform data source feature. 

First, you need to define a data source block in the application tier Terraform code that references the state file of the base network infrastructure tier. This can be done using the "terraform_remote_state" data source type. 

Next, you can specify the specific parameter that you want to retrieve from the base network infrastructure tier state file using the appropriate attribute syntax





## System Architecture and Application Design, Cloud Computing (AWS)

1. In terms of network connection between a client and a server, describe the following;
https://tldp.org/HOWTO/TCP-Keepalive-HOWTO/overview.html
https://www.keyfactor.com/blog/what-is-tls-handshake-how-does-it-work/

* Connection sessions
* TCP handshake
* TLS handshake
* TCP Keepalive
## TCP handshake is the process of establishing a connection between two devices over a TCP/IP network. It involves a three-way communication between the client and server to synchronize and establish the connection. The three steps involved in the TCP handshake are SYN, SYN-ACK, and ACK.

TLS handshake is the process of establishing a secure connection between a client and server over a network using the Transport Layer Security (TLS) protocol. The TLS handshake involves a series of steps to authenticate both the client and server, negotiate encryption algorithms, and establish a secure connection. The steps involved in the TLS handshake are Hello, Certificate, Server Key Exchange, Client Key Exchange, Certificate Verify, Change Cipher Spec, and Finished.

TCP Keepalive is a mechanism used to ensure that a TCP connection remains active and does not time out due to inactivity or network issues. It involves sending small packets at regular intervals to check if the other end of the connection is still active. If no response is received after several attempts, the connection is considered lost and closed. The frequency of TCP Keepalive packets can be configured based on the requirements of the application or network.

A connection session refers to the period of time during which a client and server maintain an active connection and exchange data over a network. A connection session can be established using various protocols, such as TCP, TLS, HTTP, FTP, etc. During a connection session, data is transmitted between the client and server in packets or frames, and the connection is terminated when the session is completed or closed by either party. Connection sessions are used in various applications, such as web browsing, email, file transfer, video streaming, online gaming, and more.

2. Your technical requirement calls for a full end-2-end encryption of traffic between the client and backend servers through an AWS Application Load Balancer. Describe how you would set up this configuration.
## 1. Create a certificate using AWS Certificate Manager or import an existing certificate.
2. Configure the Application Load Balancer to use HTTPS protocol for incoming traffic.
3. Attach the certificate to the Application Load Balancer.
4. Configure the backend servers to use HTTPS protocol for outgoing traffic.
5. Install the certificate on the backend servers.
6. Configure the security group for the backend servers to allow incoming traffic only from the Application Load Balancer.
7. Test the connection between the client and backend servers to ensure that data can be transmitted securely without any issues.
8. Monitor the performance of the Application Load Balancer and backend servers to identify any issues and optimize the configuration as needed.

3. How does the AWS Application Load Balancer determine which are the healthy backend servers to route traffic to? (Check this docuement https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html)
## The AWS Application Load Balancer uses a health check mechanism to determine which backend servers are healthy and available to receive traffic. The health check mechanism periodically sends requests to the backend servers to ensure that they are responding correctly. If a backend server fails the health check, it is marked as unhealthy and traffic is not routed to it until it passes the health check again. The health check configuration can be customized to suit specific application requirements, including the protocol, port, and endpoint used for the health check requests.

4. The main configurable components of the AWS Application Load Balancers are given below. Describe each of these and how they are related to one another.
* Listeners
* Target groups
* Targets
* Elastic Load Balancer nodes
* Health Checks
# 

5. Research these infrastructure components and why you might use each in your solutions architecture;
* A Proxy Load Balancer
* A PassThru Load Balancer
* A reverse proxy

6. Why might you want to use a TLS certificate in a solution architecture?


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
