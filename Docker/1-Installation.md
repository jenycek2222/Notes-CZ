#TEST 
1. Docker is a programming language
	1. True
	2. **False**
2. Docker is a way to define and run
	1. applications
	2. environment
	3. **both**
3. Which shares an underlying operating system?
	1. **Docker container**
	2. Virtual machine
4. What are two main sections in the output of the 'docker version' command?
	1. Client and Container
	2. Image and Container
	3. **Client and Server**
	4. Image and Server
5. Which service might you use as an alternative to the Docker Hub?
	1. GitHub
	2. **ECR**
	3. Kubernetes
	4. Docker Swarm
6. 



#INTRODUCTION
![[Pasted image 20230208124947.png]]
- virtual machines - virtualizing operating system and applications
![[Pasted image 20230208125033.png]]
- containers - don't need to virtualize another operating system
- containers are much faster to deploy and don't consume much resources, because they don't have to run another chunky operating system
#INSTALLATION
- there are three main parts of docker:
	- Docker Server/Docker Daemon - the backbone
	- Docker CLI - interaction with the server using command prompt
	- Docker GUI - interaction with the server using buttons and GUI (Docker Desktop)
#DOCKER_HUB
- Docker Hub is the place, where people and companies can put their official containers for other people to download (such as MySQL database container, which includes MySQL database installation)
- there are some alternatives to the Docker Hub - AWS's (Amazon Web Services) ECR (Elastic Container Registry) or GCP's (Google Cloud Provider) Container Registry

