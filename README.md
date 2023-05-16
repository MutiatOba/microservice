### What is a miscorservice?
A microservice is a software architectural style that structures an application as a collection of small, loosely coupled, and independently deployable services. Each microservice represents a specific business capability and operates as a separate, self-contained unit.

<img width="476" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/00988add-5f2e-47c0-b605-6532c4fb4753">


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

Docker helps us to build miscroservices

Docker hub = docker registry

- Docker client - whoever has docker on machine
- How to communicate - usual commands
- ```docker run``` - pull it down and run it
- ```docker pull``` - just pulls 
- ```docker build``` - build miscroservices using a docker image
Each command runs an API behind the scenes . When you run the run and pull command a local check is done first and if not found, then a check is done on the registry.

To find the latest images on the registry, so to docker hub: click on explore - shows you avaiable images - under trusted contect click ```docker official image``` and ```verified images``` to search for images.

#### steps: 
Here are a few of the key commands: 
- ```docker images``` - shows us the images
- ```docker ps``` - shows us the containers running
- ```docker stop <container id>``` - stops the container - so if go to webbrower then gone
- ```docker start <cointer id>``` - restrart
- ``` docker rm <cointiner id> -f```- to permanently remove the container

1. Go to gitbash
docker run hello-world [hello-world is the name of the image]

<img width="443" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/daf19ec6-2258-42e2-8690-a50b2bcd5abe">

2. To find the image - ```docker images``` 
<img width="369" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/ce8fb229-2a83-41ff-a9dd-338482d9a860">

3. to create an nginx image: 
```docker run -d -p 80:80 nginx``` [is used to run a Docker container based on the NGINX image and map port 80 of the container to port 80 of the host machine. -d stands for "detached" mode, which means the container runs in the background and doesn't attach to the current terminal session. This allows you to continue using the terminal without the container's output being displayed. -p 80:80: This option specifies port mapping, where the first value 80 represents the port on the host machine, and the second 80 represents the port inside the container. In this case, it maps port 80 of the host to port 80 of the NGINX container. This allows you to access the NGINX web server running inside the container through port 80 of your host machine  ]
<img width="439" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/2c426125-b50b-47da-9548-f2c705d2db0c">

4. To enter the container shell:
- type: ```alias docker="winpty docker"```
- ```docker exec -it <contaienr id> sh```
<img width="686" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/a97b5d88-1cd4-4528-af43-0a03543e6197">


<img width="270" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/5d776280-b939-4f4f-bd05-d2636443c6b7">

- Need to do a ```apt update``` and can access the index.html file by cd into the following directory: /usr/share/nginx/html
<img width="229" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/9af257e0-bb90-4d54-a3e1-32bedf80d18d">

- In the above directory you will find two files one including the index.html file
- go to brower: http://localhost
<img width="549" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/27860087-c57d-4baf-8da1-2648e943ddc6">


<img width="423" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/3097951f-173f-4bc4-a166-51553d984a95">

### Creating a docker image from a container

1. create a file locally called index.html

<img width="251" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/89e43063-71eb-46ef-bd30-c30cd5592251">


2. cd to where the index file is saved and type command:
```docker cp index.html 966b13e83ae6:usr/share/nginx/html```

type this in the browser: localhost:80 - shows you the new index.html file content (instead of nginx)

3. create image based on an existing container:
```docker commit 966b13e83ae6 mutiat_profile:latest```
After executing the command, Docker will create the new image using the current state of the container.

4. to see list of docker images you have created locally:
```docker images```

5. create a repository in docker hub

6. Tag your Docker image: Before pushing the image, you should tag it with the appropriate Docker Hub repository name. The general format for tagging an image is <dockerhub_username>/<repository_name>:<tag>:

```docker tag mutiat_profile:latest mutioba/profile:latest```

7. login to docker. This command will prompt you for your Docker Hub username and password
```docker login```

8. push to docker - nce you have tagged your image and logged in to Docker Hub, you can push the image using the docker push command

```docker push mutioba/profile:latest```
  
Once the push is successful, the image will be available in your Docker Hub repository and can be pulled by others or used in other systems.
  
9. to pull the image from docker hub: ```docker pull mutioba/profile:latest```

  
### Automate creating a docker image

1. navigate to where we have index.html file saved

2. Create a file called Dockerfile - ```touch Dockerfile```

3. enter into Dockerfile - ```nano Dockerfile```
  
<img width="246" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/9d7236b2-2946-4d02-9f43-b77f48851b2a">

  
4  make sure that you are not using port 80 by stopping any container runing on this port (do ```docker ps```)

5. create the image: ```docker build -t mutioba/tech221-nginx:v1 .```

6. check images are there: ```docker images```

7. create container: ```docker run -d -p 90:80 mutioba/tech221-nginx:v1```

8. do docker push: ```docker push mutioba/tech221-nginx:v1```

9. type into your webbrower: localhost:90 - will show you your updated index.html

### Creating a Docker file for APP
  
1. navigate to where app folder is saved

2. Create a file called Dockerfile - ```touch Dockerfile```

3. enter into Dockerfile - ```nano Dockerfile```

 <img width="364" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/2362090f-e338-4ba5-8ca8-ad3efa7077db">



4. create the image: ```docker build -t mutioba/appx:v2 .```

5. check images are there: ```docker images```

6. create container: ```docker run -d -p 3000:3000 mutioba/app:v2```

7. do docker push: ```docker push mutioba/app:v2```

8. type into your webbrower: localhost:3000 - will show you your app

  <img width="541" alt="image" src="https://github.com/MutiatOba/microservice/assets/118978642/2d0a0d0e-ee46-4282-be06-edc446a0c8bb">
