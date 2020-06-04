---
name: 'basic_docker'
title: Getting Started Docker
author: Jose Rodriguez
date: April 15 2020
updated: June 4 2020
id: 'basic_docker'
description: |
  Here I will cover what are the basics of docker that I will be refering to in the next tutorials.
---

# Docker basics
Here I will cover what are the basics of docker that I will be refering to in the next tutorials. This will be the entry point of the series of documents pertaining to building an automated insfratructure.

## Content
1. [ What's a docker container? ](#what)
2. [ Why would I would want to use a docker container? ](#why)
3. [ What happens when we create a container? ](#whathappens)
4. [ Basic commands ](#commands)
5. [ Creating a basic container ](#creating)
6. [ References ](#references)

<a name="what"></a>

### What is a docker container?
 You can think of it as a system or application wrapped into an image containing all the dependencies it needs to run. As an example think of a Java application, this application needs JDK and an environment, if a container is created it will have all this already within the image so you can just run that image as is without having to install anything else in your system. Once this image is ran you have an instance of the system/application. See image below for reference. 


<a name="why"></a>

### Why use images and containers?

The main advantage is scalability and ease of development. These can run on most operating systems.

<a name="whathappens"></a>

### What happens when we create container?
When we create a container we make an image come to life. The way the snapshot was saved will come to live once again and is like starting from that point in the process.

<!-- <img src="~/assets/images/containers.png" alt="Image of container stack" class="testing"> -->

[Credits](https://www.docker.com/sites/default/files/d8/styles/large/public/2018-11/container-what-is-container.png)

<a name="commands"></a>

### Basic Commands 

- Use `docker` to display a list of commands that can be used with docker. 
- Use `docker pull IMAGE_NAME` to pull an image with the given name from a private repository or dockerhub. Ex: `docker pull jenkins/jenkins`, to get a jenkins image.
- Use `docker images` to display the list of images installed in the system.
- Use `docker run [OPTIONS] IMAGE [COMMAND] [ARG...]`, to run an image providing specific arguments or options as necesary. The most used for me as far as options go are the `-itd`, the -i option keeps STDIN open even if not attached, the -t option allocates a pseudo-TTY, and the -d option runs the container in background and prints its container ID. Ex: `docker run -itd -p 80:80 -name jenkins jenkins/jenkins`, in this command I also give it a port with the -p argument.
- Use `docker ps -a` to display all containers including exited ones. To be exited a container either finished the task it was meant to do or exited with an error. 
- Use `docker logs CONTAINER_ID` to display information that the container prints as in for of echo statements or print statements, depending on he application type.
- Use `docker exec [OPTIONS] CONTAINER COMMAND [ARG...]` to run a command on given container or to go inside such container. Ex: `docker exec -it ID sh`, it will exec `sh` on the container, to be able to run more commands iff it has `sh` installed.

All the information for the above commands can be found in the docker cli reference [here](https://docs.docker.com/engine/reference/commandline/cli/).
<a name="creating"></a>

## Creating and running a simple image
The most simple Dockerfile will look as follows
```
FROM scratch
ADD hello /
CMD ["/hello"]
```
Create a file named Dockerfile and paste the above commands. FROM is where the application gets its base image, in this case we tell it to use the simplest image there is that will just run an executable. Second we add the files to the root path, third we run the program with CMD once the container is ran.

The scratch image contains the most basic tools to be able to run an executable, it must be compiled to run in such depending on the machine you use to run at as displayed in this [git repo](https://github.com/docker-library/hello-world). 

We then go where the Dockerfile is saved and run the following command `docker build --tag hello .`. That creates an image named hello with the current context and Dockerfile as indicated by the dot. 

Lastly we run the container with the following command `docker run --rm hello`. It should just display the contents and exit. 

In case you don't know how to create an executable follow the instructions on this [page](https://docs.docker.com/develop/develop-images/baseimages/) most likely you don't have to start from scratch. 

If there's any questions you can reach out to me or post them in the comments below.

<a name="references"></a>

### References
- [docker](https://www.docker.com/resources/what-container)
- [oracle win32](https://docs.oracle.com/javase/tutorial/getStarted/cupojava/win32.html)
- [stackify docker](https://stackify.com/docker-image-vs-container-everything-you-need-to-know/)
- [google containers](https://cloud.google.com/containers)
- [docker base image](https://docs.docker.com/develop/develop-images/baseimages/)