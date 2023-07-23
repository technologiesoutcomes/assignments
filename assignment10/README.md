1. Provide you understanding of the following terminologies;
* idempotency
* synchronous
* asynchronous
* cohesive architectures
* coupled/decoupled architectures
* microservice architectures
* network latency
* network throughput
* resilient architecture
* highly available architecture
* mutable architecture (Pet)
* immutable architecture (Cattle)
* ephemeral 
* scaling - horizontal, Vertical
* Serverless architectures
* Managed services architectures
1. Idempotency: Refers to the property of an operation that can be repeated multiple times without changing the result beyond the initial application. In other words, if an operation is idempotent, it will produce the same result every time it is executed, regardless of how many times it is executed.

2. Synchronous: Refers to a type of communication between two or more systems where the sender waits for a response from the receiver before proceeding with the next step.

3. Asynchronous: Refers to a type of communication between two or more systems where the sender does not wait for a response from the receiver before proceeding with the next step.

4. Cohesive architectures: Refers to an architecture where each component or module has a clear and well-defined responsibility and works together seamlessly to achieve a common goal.

5. Coupled/decoupled architectures: Refers to the degree of interdependence between components or modules in an architecture. A coupled architecture has high interdependence between components, while a decoupled architecture has low interdependence between components.

6. Microservice architectures: Refers to an architecture where an application is broken down into small, independent services that communicate with each other through APIs.

7. Network latency: Refers to the delay that occurs when data is transmitted over a network.

8. Network throughput: Refers to the amount of data that can be transmitted over a network in a given amount of time.

9. Resilient architecture: Refers to an architecture that is designed to continue functioning even in the face of failures or disruptions.

10. Highly available architecture: Refers to an architecture that is designed to minimize downtime and ensure that services are always available to users.

11. Mutable architecture (Pet): Refers to an architecture where servers are treated as individual pets that need to be cared for and maintained over a long period of time.

12. Immutable architecture (Cattle): Refers to an architecture where servers are treated as disposable resources that can be easily replaced or destroyed.

13. Ephemeral: Refers to something that is short-lived or temporary.

14. Scaling - horizontal, vertical: Refers to the process of increasing or decreasing the capacity of a system to handle varying levels of demand. Horizontal scaling involves adding more instances or nodes to a system, while vertical scaling involves increasing the resources (e.g. CPU, RAM) of existing instances or nodes.

15. Serverless architectures: Refers to an architecture where applications are built using cloud-based services and functions that are executed on demand, without the need for dedicated servers.

16. Managed services architectures: Refers to an architecture where third-party providers offer managed services that handle various aspects of an application's infrastructure, such as databases, caching, and load balancing.

2. Read the following AWS articles and answer the questions that follow;

* https://aws.amazon.com/what-is/eda/
* https://aws.amazon.com/blogs/architecture/lets-architect-designing-event-driven-architectures/

* What technologies are used to enable communication between services in an EDA architecture? The technologies used to enable communication between services in an EDA architecture include message brokers, event buses, and APIs. These technologies allow services to publish and subscribe to events, send and receive messages, and make requests and responses.

* Describe why decoupled services are better able to scale than highly coupled services 
Decoupled services are better able to scale than highly coupled services because they have low interdependence between components, which allows them to be easily added or removed as needed. In a highly coupled architecture, changes to one component can have a ripple effect on other components, making it difficult to scale without causing disruptions or downtime. Decoupling also allows for more flexibility in choosing the technology stack for each service, as they are not tightly integrated with each other


3. Implement the following;
```
cd technologiesoutcomes

mkdir dockersamples

cd dockersamples

git clone https://github.com/dockersamples/buildme.git

cd buildme

sudo docker build --tag=buildme .
sudo docker run --name=buildme --rm --detach buildme
sudo docker exec -it buildme /bin/client
sudo docker stop buildme

sudo docker build --tag=buildme2 -f chapters/2.Dockerfile .
sudo docker build --tag=buildme3 -f chapters/3.Dockerfile .
sudo docker build --tag=buildme4 -f chapters/4.Dockerfile .

```
