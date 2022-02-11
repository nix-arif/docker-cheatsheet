# Docker Cheatsheet

# Problem Statement

- We have end to end application stack including various technologies like web server using nodejs, database such as MongoDB, messaging system like Redis and orchestration tool like Ansible, we had a lot issues developing this application stack with all these different components.
- First of all, the compatibility with the underlying OS is an issue, we had to ensure that all these different services are compatible with the version of OS we were planning to use. There have been times where certain version of the services are not compatible with the OS, and we have to go back and look at different OS that is compatibel with all of these services.
- Secondly, we need to check the compatibility between the services and the libraries and dependencies on the OS. We have issues where one service requires one version of a dependent library, whereas another service requires another version, the architechure of our application changed over time, we have to upgrade to newer version of these components, or change the database, etc. And every time something changed, we have to go through the same process of checking compatibility between these various components, and the underlying infrastructure. This compatibility matrix issue is usually referred to as the matrix from hell.
- Thirdly,

# What are Containers

# What is Docker
