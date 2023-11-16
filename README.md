Nov.15, 2023

## What is a Docker

1. A platform for building, running, and shipping applications
   - Container
2. Docker helps in consistently build, run, and ship applications

Why some machine works?

- One or more files missing
- Software version mismatch
- Different configuration settings

```python
docker-compose up

docker-compose down --rmi all
```

## VM vs Container

1. Container: An isolated environment for running an application
   - Allow running multiple apps in isolation
   - Are lightweight
   - Use OS of the host - Start quick
   - Need less hardware resources
1. VM: An abstraction of a machine (physical hardware)
   - Hypervisors: VirtualBox, VMware, Hyper-v(Windows only)
   - Run applications in isolation

- Problems:
  - Each VM needs a full-blown OS
  - Slow to start
  - Resource intensive

## Docker Architecture

1. Client Server. Server: Docker Engine
   Client -Rest API -> Server (Docker Engine)
2. It is a process running
3. All the container share the kernel(manages applications and hardware resources) of an operation system
   ![[Screenshot 2023-11-15 at 6.12.19 PM.png]]

## Installing Docker

![[Screenshot 2023-11-15 at 6.46.47 PM.png]]

## Development workflow

1. Dockerfile in applications -> package the application into an image (Everything the application needs to run)
2. Image
   - A cut-down OS
   - A runtime environment (e.g: Node)
   - Application files
   - Third-party libraries
   - Environment variables
3. We tell Docker to start the image with its container

```python
# instead of
my-app
# using docker to run in its own image
docker run # in an isolated environment

```

4. Once we have the image, we can push it into Registry (Docker Hub) i.e Github to git -> put on any machines running docker

5. All the instructions for building an image of an application are written in a docker file

## Docker in action

```python
node app.js # to get the console log output
```

## Deploy the program

1. Start with an OS
2. Install Node
3. Copy app files
4. Run node app.js

- Some images names are officially published on DockerHub
- There are multiple node images, these node images are built on the top of different distributions of Linux

```python
node:apline # is a very small image
WORKDIR /app # Clearly describe that it is in the /app directory

# '.' to reference the current directory
docker build -t hello-docker .

# Take a look at docker images
docker image ls

# Run the image
docker run hello-docker
```

- An image is not a single file.

```python
# Run already-built dockers
docker pull codewithmosh/hello-docker

# See all docker images
docker image ls

# From any machine
docker run codewithmosh/hello-docker
```

## Linux Distributions

1. Open Source software
2. Distros: Ubuntu, Debian, Alpine, Fedora, CentOS

## Running Linux

```python
# Docker starts a container
docker run ubuntu

# See running containers
docker ps
docker ps -a # for all

docker run -it ubuntu # start the container in the interactive mode
# /#root login as a normal user
echo hello
whoami

echo $0 # see the location of the program

# Linux is a case-sensitive system
history # See all the commands
!2 #exactly 2 commands
```

## Managing Packages

1. package managers

   - npm
   - yarn
   - pip

2. apt for Ubuntu
   - apt-get
3. nano: basic text for Linux

```python
# See all packages in this database
apt list

# update the package database
apt update # ALWAYS RUN THIS before installing package

# install nano
apt install nano

# Text editor
nano

# Remove the package
apt remove nano
```
