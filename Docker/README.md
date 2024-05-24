# Docker setup on linux machine	
  ```
sudo yum update		: To update os
sudo yum install docker.io	: To install docker on linux
sudo usermod -aG docker ec2-user/linux	: No need to use sudo
systemctl is the systemd command for controlling how services start on a Linux system
sudo systemctl status docker	: to know status of service
systemctl start docker	: To active service
docker --version	: To check version
docker pull <image name>: To pull or download image from remote (dockerhub)
docker images		: To list all Docker images
docker pull centos:7.9.2009	: To pull centos with version
docker ps		: list running containers
dacker ps -a		: list all containers
sudo docker run 	: create container from image
docker run -it <image name:version>	: to login and tag to container
cat /ect/redhat-release	: To know the version
yum install git		: To install git
ctrl+p & ctrl+q		: To come out from container for first time
docker ps 		: To list docker container
```


# To Create Docker File & Image	
```
sudo vi <Dockerfile> 	: To create docker file
>>> In "Dockerfile" Instructions
>>FROM centos:7.9.2009
>>WORKDIR /opt
>>RUN yum install git -y
>>RUN yum install java -y
>>#To install app directly
>>COPY /home/ec2-user/sample.conf /opt 	: To copy sample.conf to cointainer

sudo docker build	: To create docker image from docker file
sudo docker build -t <imagename:version> <path/ .> : 
>>> Dockerfile instructions will executive step by step
>>>after completing of execution successfully build & tag docker images
sudo docker images 	: To show the docker images
sudo docker run -it myimage:1.0	: To enter in to docker container
cat /ect/redhat-release	: To check the given os
git --version		: check git installed or not
java -version		: check java installed or not
sudo docker rmi <imagename:version>	: To removie image
sudo docker tag <imagename:version> <New name:version>	: To rename and copy the image
```


# To create Docker Container	
 ```
sudo docker exec -it <imageid> /bin/bash : To enter into container
ctrl+p & ctrl+q		: To come out from container for first time
exit			: To come out from container after time
Sudo docker inspect <containerid>	: shows full info of cointainer & ip adress
sudo docker logs <containerid>		: it shows all activities
sudo docker container stop <containerid>: To stop docker cointainer
sudo docker container start <containerid>: To start docker cointainer
sudo docker run -dt <myimage:1.0>	: To create docker in detached mode
sudo docker attach <cointainer id>	: To enter into container
sudo docker exec -it <container id> 	: connect and run commands
sudo docker exec <container id> ls/opt	: To run command without enter to container
sudo docker rm <cointainer id> 		: To delete container
```


# To create Docker Registry	
```  
In AWS - ECR-Elastic Container Registry
In Azure - ACR-Azure Container Registry

Docker.io/library/myimage  : This is format to to push image to repo
docker.registry/username/imagename : format of your docker image
sudo docker run -it <cointainer id url link>	: pull from remote repo
sudo apt install awscli		: To install aws cli
aws configure 		: Configure with aws
create repo in aws account -> in Elastic cointainer Registry
Follow aws [view push commands] To push images
authenticate using aws cli
docker tag <local Image Name:Version> <url from remote> : To tag
docker push <url from remote> 	: To push local to remote
docker pull <url in remote> 	: To download Docker image
```


# To create Volumes	
```
docker volume ls		: To list volumes
docker volume create <name>	: To create volume
docker volume inspect <name>	: To inspect details of volume
Refer from git Repo		: /Docker-Zero-to-Hero/examples/first-docker-file$
docker build -t volumedemo .	: To build volume from docker file
docker volume create Teja	: To create volume
docker run -d --mount source=Teja,target=/app nginx:latest	: running the container with a mount
docker inspect <container id>	: To know details/ip address of container
if you want to delete volume  	: Stop the container,Delete the container and Delete volume 
docker volume rm <name>		: To delete volume
```


# Docker Networking	
```
Refer from git Repo 	: /Docker-Zero-to-Hero/examples$
docker run -d --name login nginx:latest	: To create container
docker exec -it login /bin/bash		: To enter into container
apt update				: To update os
apt install iputils-ping		: To install ping on ubuntu
docker run -d --name logout nginx:latest: To create another container
docker inspect <container name> 	: To check ip address/details
docker network ls			: To list networks
docker network rm <name>		: To delete network
docker network create secure-network	: To create secure network
docker run -d --name finance --network=secure-network nginx:latest  : to secure finance container
docker run -d --name host-demo --network=host nginx:latest	: To create host network 
```
# Docker Bridge Networking
```
Ip address are difference in bridge, hosh and secure network drivers.
Bridge is default.
Enter into the login container enter command (ping <ip address> : to communicate) 
of logout container to communicate with each other but when you enter finance <ip address>
will not communicate, because finance container is secure.
```


