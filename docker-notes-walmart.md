13-Oct-2023
-----------------
Topic: Docker (DevOps)


Why Docker
	- Its a means of Containarization 
	- To Deploy the code + Cost optimization 
	- Main the application cost(Resource) + platform 
	- Its ligher than VM 
	- Easy to deploy MicroService based application 
	- Dependencies of application can be maintained easily (no)
	- Bundle only the required resources for the application and deploy in sysytem
	- Independent installation of the applications ()
	- To run the application anywhere



docker pull hello-world:nanoserver-ltsc2022
docker pull hello-world -> then latest version of docker is given for that image 
docker pull open-jdk -> latest version 
	

> docker pull hello-world
> docker start hello-world 

or 

>docker run hello-world - if the image is not found locally then it will put from repository 




- docker -v 
- docker version (full information)
- docker info 
- docker --help 
- docker container --help
- docker images --help
- docker login 




- docker is containarization tool
	- for orchestration you can use
		- Kubernetes 
		- Rancher 
		- GitLab
		- Docker Swarm 

- docker networking 
	- single host - for 1 host
	- by default bridge network 
	- orverlay for multi for communication 
	- macvlan - 

- docker network 
- docker network create my-network 


> https://collabnix.com/docker-cheatsheet/



Day 2 - 14-Oct-2023
-------------------------------------



- in files Dockerfile 
	```
		> java -jar myjar.jar 

		> java -cp myjar.jar com.naveen.App
	```
- i need react application / java application to be docerized 
	> docker run -p 9090:9090 walmart/spring-app-1
	> docker run -p 9090:9090 -p 9080:9090 walmart/spring-app-1

	> docker run -p 9090:9090 adithnaveen/walmart-spring-app-1:1
	> goto browser http://localhost:9090/hello


	> docker run -p 7090:9090 ksvsbdocker/walmart-spring-app-1:1
- i need 2 instances of mongo 
- in need an instance but it should be persisted - volumes 
- port mapping for docker containers 
	- jenkins 8080 -p 
- push the images to docker hub and others can run it 
	- Step 1 > docker build -f Dockerfile -t walmart/spring-application:1 
	- Step 2 > docker images (You will find walmart/spring-application:1 )
	- Step 3 > docker image tag walmart/spring-application:1 adithnaveen/myapp:1 
	- Step 4 - docker push adithnaveen/myapp:1 
	- step 5  - on other system 
		> docker run -p hostport:dockerport adithnaveen/myapp:1

- connect one container with another container 
	> Step 1: docker network create walmart-network 
	> Step 2: docker run -itd --name walmart-ubuntu-1 --network walmart-network ubuntu:latest 
	> Step 3: docker run -itd --name walmart-ubuntu-2 --network walmart-network ubuntu:latest 
	> Step 4: docker network inspect walmart-network 
	> Step 5: get into walmart-ubuntu-1
		> docker exec -it walmart-ubuntu-1 /bin/bash
	> Step 6: apt update 
	> Step 7 : apt install iputils-ping 
	> Step 8 : ping walmart-ubuntu-2





References 
---------------------------------- 

 > https://hub.docker.com/_/busybox 

> https://docs.docker.com/engine/reference/builder/ - docker file 