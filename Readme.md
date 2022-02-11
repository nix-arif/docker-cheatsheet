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

# What is Docker
