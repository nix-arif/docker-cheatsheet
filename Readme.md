# Docker Cheatsheet

# Problem Statement

- We have end to end application stack including various technologies like web server using nodejs, database such as MongoDB, messaging system like Redis and orchestration tool like Ansible, we had a lot issues developing this application stack with all these different components.
- First of all, the compatibility with the underlying OS is an issue, we had to ensure that all these different services are compatible with the version of OS we were planning to use. There have been times where certain version of the services are not compatible with the OS, and we have to go back and look at different OS that is compatibel with all of these services.
- Secondly, we need to check the compatibility between the services and the libraries and dependencies on the OS. We have issues where one service requires one version of a dependent library, whereas another service requires another version, the architechure of our application changed over time, we have to upgrade to newer version of these components, or change the database, etc. And every time something changed, we have to go through the same process of checking compatibility between these various components, and the underlying infrastructure. This compatibility matrix issue is usually referred to as the matrix from hell.
- Thirdly, every time we had a new developer on board, we found it really difficult to set up a new environment, the new developers had to follow a large set of instructions and run hundreds of commands to finally setup their environment. We have to make sure they were using the right operating system, the right versions of each of these components. And each developer had to set all that up by himself each time. He also had different development, tests and production environments. One developer maybe comfortable using one OS and the others maybe comfortable using another OS. And we couldn't guarantee that the application that we were building will run the same way in different environment.
- With all these problems, it make our life in developing better building and shipping the application really difficult.
- So we need something that could help us with the compatibilty issues and something that will allow us to modify or change these components without affecting the other components and even modify the underlying operating systems as required.

# How Docker Solve All the Problems

- With Docker, we can run each component in a saparate container with its own dependencies and its own libraries, all on the same VM and the OS but within seperate environments or containers. We just had to build the Docker configuration once and all our developers could now just get started with a simple Docker run command.

# What are Containers

- Containers are completely isolated environments, as they can have their own processes or services, their own network interfaces, their own mounts, just like virtual machine except they all share the same OS kernel.

# What is Docker

# Installing Docker on Linux (Convenience script)

- https://docs.docker.com/engine/install/ubuntu/
- Confirming version of ubuntu linux distro ex. bionic, focal.

```
cat /etc/*release*
```

<img src="./Linux Focal Distro.png" alt="Linux Focal Distro">
- Uninstall older docker version if one exist.
```
 sudo apt-get remove docker docker-engine docker.io containerd runc
```

- Install with convevience script

```
 curl -fsSL https://get.docker.com -o get-docker.sh
 sudo sh get-docker.sh
```

- Checking the docker version after the installation finish

```
sudo docker version
```

# Testing the Docker

- Find an image from dockerhub https://hub.docker.com/
- Using popular image to test whalesay

```
docker run docker/whalesay cowsay Hello-World
```

### docker run nginx -> running a container from an image. If image doesn't exist locally in the docker host, it will pull from dockerhub.

### docker ps -> list all running containers and shows some basic information about them eg. containerId, status.

### docker ps -s -> listing all running and stop containers.

### docker stop [id@name] -> used to stop a running container, need to provide container id or name of that container

### docker rm [id@name] -> used to remove a stopped or exited container permanently

### docker images -> used to see all images on docker host

### docker rmi [image] -> delete an image in docker host. Ensure that no containers off that image before attempting to remove

### docker pull [image] -> pull image and store in docker host

### docker run ubuntu sleep 100 -> instruct docker to run a process eg. sleep ubuntu for 100 seconds

### docker exec [containername] cat /etc/hosts -> used to execute a command on running docker container. In this case, to print the content of `/etc/hosts` file

### docker inspect [containername]

### docker logs [containername]

### docker run -e APP_COLOR=blue simple-webapp-color -> environment variable

### docker inpect [containername] -> search under Config -> Env -> Searching for environment variable
