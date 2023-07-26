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

First, you need to define a data source block in the application tier Terraform code that references the state file of the base network infrastructure tier. This can be done using the "terraform remote state" data source type. 






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
#Listeners: A listener is a component of the AWS Application Load Balancer that listens for incoming traffic and directs it to the appropriate target group. A listener is configured with a protocol (HTTP, HTTPS, TCP, etc.), a port number, and a set of rules that define how incoming traffic should be routed.

Target groups: A target group is a logical grouping of backend servers that receive traffic from a specific listener. Each target group is associated with a specific protocol and port number. The AWS Application Load Balancer routes incoming traffic to the appropriate target group based on the rules defined in the listener configuration.

Targets: A target is an instance of a backend server that is registered with a specific target group. Targets can be EC2 instances, containers, IP addresses, or Lambda functions. The AWS Application Load Balancer distributes incoming traffic across all healthy targets in a target group.

Elastic Load Balancer nodes: The AWS Application Load Balancer is implemented as a highly available service that runs on multiple nodes. Each node is responsible for processing incoming traffic and forwarding it to the appropriate backend server. The Elastic Load Balancer nodes work together to provide high availability and scalability for the load balancer service.

Health Checks: Health checks are used by the AWS Application Load Balancer to determine which backend servers are healthy and available to receive traffic. The health check mechanism periodically sends requests to each target in a target group to ensure that it is responding correctly. If a target fails the health check, it is marked as unhealthy and traffic is not routed to it until it passes the health check again. The health check configuration can be customized to suit specific application requirements. 

5. Research these infrastructure components and why you might use each in your solutions architecture;
* A Proxy Load Balancer
* A PassThru Load Balancer
* A reverse proxy
1. Proxy Load Balancer: A proxy load balancer is a type of load balancer that sits between the client and the server. It receives requests from clients and forwards them to the appropriate server based on a set of predefined rules. This type of load balancer is useful in scenarios where there are multiple servers that need to be balanced, and where the servers are not directly accessible by the clients. The proxy load balancer can be used to distribute traffic evenly across multiple servers, ensuring that no single server is overloaded.

2. PassThru Load Balancer: A pass-thru load balancer is a type of load balancer that simply passes requests through to the appropriate server without modifying them in any way. This type of load balancer is useful in scenarios where there are multiple servers that need to be balanced, but where the servers are already load balanced at a lower level (such as at the application layer). The pass-thru load balancer can be used to distribute traffic evenly across multiple servers, without adding any additional overhead or complexity.

3. Reverse Proxy: A reverse proxy is a type of proxy server that sits between the client and the server, and is used to provide additional functionality such as load balancing, caching, and security. This type of infrastructure component is useful in scenarios where there are multiple servers that need to be balanced, and where additional functionality such as caching or security is required. The reverse proxy can be used to distribute traffic evenly across multiple servers, while also providing additional functionality such as SSL termination or content caching.


6. Why might you want to use a TLS certificate in a solution architecture?
A TLS (Transport Layer Security) certificate is used to secure communication between two endpoints over the internet. Here are some reasons why you might want to use a TLS certificate in a solution architecture:

1. Authentication: A TLS certificate can be used to authenticate the identity of the server or client. This ensures that the communication is secure and that the data is not intercepted by a third party.

2. Encryption: A TLS certificate encrypts the data being transmitted between the two endpoints. This ensures that the data cannot be intercepted and read by an unauthorized party.

3. Trust: A TLS certificate is issued by a trusted third party, such as a Certificate Authority (CA). This ensures that the communication is secure and that the data is not tampered with.

4. Compliance: Many regulations, such as PCI DSS, require the use of TLS certificates to secure communication between endpoints.

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
