### What is a miscorservice?
A microservice is a software architectural style that structures an application as a collection of small, loosely coupled, and independently deployable services. Each microservice represents a specific business capability and operates as a separate, self-contained unit.


### what is the difference between n-tier and microservices architecture?

N-Tier Architecture is a traditional software architectural style that divides an application into multiple logical layers or tiers. The layers typically include presentation (UI), business logic, and data storage.

Microservices Architecture, on the other hand, is a modern architectural style that structures an application as a collection of small, independent, and loosely coupled services

N-Tier Architecture:

- Monolithic application structure: The application is built as a single, interconnected unit where all layers are tightly integrated.
- Tightly coupled layers: The layers of the application have strong dependencies on each other, making it challenging to modify or replace individual components.
- Shared data and libraries: Components within a layer share the same data and libraries, leading to potential dependencies and constraints.
- Centralized database: The architecture typically uses a single, centralized database that serves all layers of the application.
- Single deployable unit: The entire application is deployed as a single unit, making it difficult to independently deploy or scale specific components.

Microservices Architecture:

- Distributed service-oriented architecture: The application is divided into separate services that operate independently and communicate with each other through well-defined APIs.
- Loosely coupled services: Each microservice is decoupled from others, allowing for independent development, deployment, and scaling.
- Communication through APIs: Microservices interact with each other using lightweight protocols and well-defined interfaces, promoting loose coupling and modularity.
- Autonomous data management per service: Each microservice can have its own dedicated database or data storage, providing autonomy and flexibility.
- Independent deployment and scaling: Microservices can be deployed and scaled independently, allowing for faster iterations and targeted scaling based on demand.

### What is Docker?

Docker is an open-source platform that enables developers to automate the deployment, scaling, and management of applications using containerization. Containers are lightweight, isolated environments that package an application and its dependencies, ensuring consistency and reproducibility across different computing environments.

<img width="466" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/3cd073f0-41e0-4516-b54c-4f4b62811bd8">


### What is containerisation?

Containerization is the process of encapsulating an application and its dependencies into a container. It involves bundling an application, along with its runtime environment, system tools, libraries, and configurations, into a self-contained unit known as a container.

The container provides an isolated and lightweight execution environment that runs consistently across different computing environments, such as development machines, testing servers, and production systems. The containerization technology achieves this by leveraging operating system-level virtualization, where multiple containers can run on a single host operating system.

### Containerisation vs Virtulisation

virtualization creates separate virtual machines that mimic entire computers, while containerization creates isolated environments that run applications using shared resources. Virtualization is like having separate houses within a building, while containerization is like having separate apartments within a building.

Virtualization:

- Virtualization is like having multiple computers within a single physical computer.
- It creates virtual machines (VMs) that act as separate computers with their own operating systems and resources.
- Each VM runs independently and can run different operating systems or software.
- VMs are more heavyweight as they require a full operating system and replicate the entire computer environment.
- Virtualization is like having multiple houses within a single building, each with its own rooms and facilities.

Containerization:

- Containerization is like having multiple isolated apartments within a single building.
- It creates containers that are lightweight and isolated environments for running applications.
- Containers share the host operating system and run as isolated processes.
- Containers are more lightweight and use fewer resources compared to virtual machines.
- Containerization is like having multiple self-contained apartments with their own kitchens, bathrooms, and utilities, all within a single building.

<img width="507" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/a38f189f-ea9b-4b4c-adfa-df5e00c409ff">

### How to use Docker
Docker image is immutable - cant change once built, this helps with versioning 

Docker helps us achieve miscroservice

Docker hub = docker registry

Docker client - whoever has docker on machine
How to communicate - usual commands
docker run - pull it down and run it
docker pull - just pulls 
docker build - build miscroservices using a docker image
They check locally first

Each command runs an API behind the scenes - if 200 responds use locally (docker host), if not then goes to the registry

Go to docker hub:
click on explore - shows you avaiable images - under trusted contect click docker office image and verified images 

Go to gitbash
docker run hello-world [hello-world is the name of the image]

<img width="443" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/daf19ec6-2258-42e2-8690-a50b2bcd5abe">

To find the image - ```docker images``` 
<img width="369" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/ce8fb229-2a83-41ff-a9dd-338482d9a860">

to create an nginx image: 
```docker run -d -p 80:80 nginx``` [connect to port 80 of my local host to its port]
<img width="439" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/2c426125-b50b-47da-9548-f2c705d2db0c">

type local host in web browser
```docker images``` - shows us the images
```docker ps``` - shows us the containers running
```docker stop <container id>``` - stops the container - so if go to webbrower then gone
```docker start <cointer id>``` - restrart
``` docker rm <cointiner id> -f```- 

To enter the container shell:
alias docker="winpty docker"
docker exec -it <contaienr id> sh
<img width="686" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/a97b5d88-1cd4-4528-af43-0a03543e6197">
<img width="270" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/5d776280-b939-4f4f-bd05-d2636443c6b7">
