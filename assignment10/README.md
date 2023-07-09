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

2. Read the following AWS articles and answer the questions that follow;

* https://aws.amazon.com/what-is/eda/
* https://aws.amazon.com/blogs/architecture/lets-architect-designing-event-driven-architectures/

* What technologies are used to enable communication between services in an EDA architecture?
* Describe why decoupled services are better able to scale than highly coupled services


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
