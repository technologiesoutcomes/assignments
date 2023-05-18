## My name is MoulesNavti Outcomer and please file below my submission

##  1) Containers and Virtual machines are two approaches to deploying applications. Name the advantages and disadvantages of each.                   
Containers and virtual machines are two popular approaches to deploying applications, each with its own advantages and disadvantages. Here are the key characteristics of each:

## Virtual Machines (VMs):

Advantages:
Isolation: VMs provide strong isolation between the host system and the virtualized environment, making them more secure. Each VM has its own operating system, runtime, and application dependencies.
Compatibility: VMs can run applications built for different operating systems, allowing you to host diverse workloads on the same physical server.
Flexibility: VMs can be easily migrated between different hypervisors or physical servers, providing flexibility in resource allocation and management.
Hardware abstraction: VMs abstract the underlying hardware, allowing applications to run consistently regardless of the physical infrastructure.


Disadvantages:
Resource overhead: Each VM requires a separate operating system instance, which consumes more resources (CPU, memory, and storage) compared to containers.
Slower startup time: VMs take longer to start and boot because they need to initialize a complete operating system.
Limited density: Due to the higher resource requirements, the number of VMs that can be hosted on a physical server is typically lower than the number of containers.
Management complexity: Managing VMs involves managing multiple operating systems, patching, and maintaining separate instances.

## Containers:

Advantages:
Lightweight: Containers share the host system's operating system kernel, resulting in smaller resource footprint and faster startup times compared to VMs.
Scalability: Containers are highly scalable, allowing easy replication and orchestration of multiple instances of an application to handle varying workloads.
Portability: Containers encapsulate applications and their dependencies, making them portable across different environments, from development to production.
DevOps integration: Containers align well with modern DevOps practices, enabling faster development cycles, continuous integration, and deployment.

Disadvantages:
Limited isolation: Containers share the host system's kernel, so if a container compromises the kernel, it could impact other containers or the host system.
Compatibility limitations: Containers are limited to running on the same operating system as the host, which can be a constraint for certain applications designed for specific operating systems.
Security concerns: Although containers provide isolation, security vulnerabilities within container images or misconfigurations can expose the host system or other containers to risks.
Tooling complexity: The ecosystem around containerization, including container orchestration platforms like Kubernetes, can have a learning curve and require additional effort to set up and manage.
It's important to note that the choice between containers and VMs depends on the specific use case, workload requirements, and infrastructure considerations. Many organizations use a combination of both to leverage their respective benefits effectively.


## 2) What is a Docker image and how are they created?
A Docker image is a lightweight, standalone software package that includes all the necessary components to run an application. It contains the application's code, dependencies, libraries, and runtime environment. Docker images are created using a Dockerfile, which specifies the steps to build the image. The Dockerfile defines instructions like copying files, installing packages, configuring settings, and running commands. When the Dockerfile is built using the docker build command, each instruction creates a new layer in the image. Layers are cached, allowing for faster subsequent builds. The resulting image is portable and can be run on any system with Docker installed. Docker images enable consistent and reproducible deployments, making it easier to package and distribute applications across different environments.

## 3) What is a Docker container and how might you run them?

A Docker container is a lightweight, standalone executable package that includes everything needed to run a piece of software, including the code, runtime, system tools, and system libraries. It provides a consistent and reproducible environment for applications to run, regardless of the underlying infrastructure.

To run Docker containers, you need to follow these steps:

Install Docker on your machine or server.
Create a Dockerfile, which is a text file that defines the configuration and dependencies of your application.
Build an image from the Dockerfile using the Docker command-line interface (CLI). This image serves as a blueprint for your container.
Run the container based on the built image using the Docker CLI. You can specify various options, such as port mapping, volume mounting, and environment variables.
The Docker engine starts the container, which runs in isolation with its own filesystem, network, and process space.
Docker containers provide a consistent and efficient way to package, deploy, and run applications, making it easier to manage and scale your software across different environments.


## New commands logs - Enter up to ten new commands you have learnt this week

| Number      | Commands | What does it do and how might you check its effect     |

1| git merge -s recursive     
The command "git merge -s recursive" is used to perform a  merge operation in Git, using the recursive merge strategy. USed when (git pull) failed 

## Glossary of the week - Enter new technical words you have learnt this week and their meanings.

| Number   | Word | Meaning     |

1) Microservices: 
An architectural style where applications are built as a collection of small, independent services that communicate with each other through well-defined APIs. Microservices enable teams to develop, deploy, and scale individual services independently, promoting flexibility and resilience in applications.