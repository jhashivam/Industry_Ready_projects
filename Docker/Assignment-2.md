# Docker & Docker Hub


### Assignment 1:

Demonstrate minimum 15 basic docker command with explanation and screenshot.

> 1: Check docker version and docker installed or not

```
docker version

docker 
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/doc_01.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc_01.png)
> 2: Pull an Image 

```
docker pull hello-world
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-03.png)


> 3: docker run command- This will first creates a writeable container layer over the specified image, and then starts
```
docker run hello-world
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-04.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-05.png)

> 4: Create Container and start container in detached mode 
**When we run this command Docker will install nginx:latest from the NGINX repository hosted on Docker Hub. I used --detached or -d because i want this container to keep running in background**
```
docker run --detach --name web nginx:latest

```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-06.png)

> 5: `docker ps` command, which lists all running containers and 5: `docker ps -a` command, which lists all running and stopped containers
```
 docker ps

 docker ps -a  
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-07.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-08.png)


> 6:`docker images` command list all the docker images are available on our Docker host

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-09.png)

> 7: Searching for images - We can search all of the publicly available images on Docker Hub using the
`docker search` command
```
docker search python
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-10.png)

> 8: Pulling down the bitnami/python image
```
docker pull bitnami/python
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-11.png)

> 9: Creating a Docker container from the bitnami/python image
```
docker run -i -t bitnami/python /bin/bash
```
**launched a new container from our bitnami/python image and container interactively and told the container to run the bash shell. Once inside the container shell i run python version comamnd where python was pre-installed on our image**

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-12.png)

> 10: Create account on docer hub and login using `docker login` command
```
docker login
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-13.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-14.png)

> 11: Building our own images . We build images using a definition file called a `Dockerfile` and the `docker build` command.
**We’ve created a directory called static_web to hold our Dockerfile. This directory is our build environment, which is what Docker calls a context or build context. Docker will upload the build context, as well as any files and directories contained in it, to our Docker daemon when the build is run. This provides the Docker daemon with direct access to any code, files or other data you might want to include in the image.**

**The Dockerfile contains a series of instructions paired with arguments. Each instruction, for example FROM, should be in upper-case and be followed by an argument: FROM ubuntu:18.04. Instructions in the Dockerfile are processed from the top down, so you should order them accordingly. Each instruction adds a new layer to the image and then commits the image.**

- Docker executing instructions roughly follow a workflow: 
    - Docker runs a container from the image.
    - instruction executes and makes a change to the container.
    - Docker runs the equivalent of docker commit to commit a new layer.
    - Docker then runs a new container from this new image.
    - The next instruction in the file is executed, and the process repeats until all instructions have been executed.`
    - The first instruction in a Dockerfile must be FROM. The FROM instruction specifies an existing image that the following instructions will operate on; this image is called the base image.
    - In this Dockerfile i have mentioned the ubuntu:18.04 image as our base image. This  will build an image on top of an Ubuntu 18.04 base operating system.
    - Next, i have mentioned the LABEL instruction with a value of ‘maintainer=“shivamjha@example.com”, which tells Docker who the author of the image is and what their email address is.
    -  The RUN instruction executes commands on the current image.
    - This is installing the nginx package and then creating the /var/www/html/index.html file.
    - By default, the RUN instruction executes inside a shell using the command wrapper /bin/sh -c.
    - I have added the EXPOSE instruction, which tells Docker that the application in this container will use this specific port on the container.
    - we can specify multiple EXPOSE instructions to mark multiple ports to be exposed.
```
$ mkdir static_web
$ cd static_web
$ touch Dockerfile
$ vim Dockerfile
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-15.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-16.png)

`Building the image from our Dockerfile`

- If we do not specify any tag, Docker will automatically tag youourr image as latest.
- The trailing . tells Docker to look in the local directory to find the Dockerfile.
```
docker build -t="shivamjha/static_web" .

```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-17.png)

> 12: Viewing newly created image from Dockerfile
```
docker images shivamjha/static_web
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-18.png)

> 13: Using the docker history command to drill down into how our image was created `docker history <image id>`

```
docker history 3f73bcafca55
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-19.png)

> 14: Launching a container from new image shivamjha/static_web

**Here I’ve launched a new container called static_web using the docker run command and the name of the image we’ve just created. We’ve specified the -d option,which tells Docker to run detached in the background. This allows us to run longrunning processes like the Nginx daemon. We’ve also specified a command for the container to run: nginx -g "daemon off;". This will launch Nginx in the foreground to run our web server. We’ve also specified a new flag, -p.The -p flag manages which network ports Docker publishes at runtime. When you run a container, Docker has two methods of assigning ports on the Docker host:**
    - This will bind port 80 on the container to port 80 on the local host.

```
docker run -d -p 80:80 --name static_web_80 shivamjha/static_web nginx -g "daemon off;"

```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-20.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-21.png)

> 15: Pushing a Docker image in Docker Hub
```
docker tag shivamjha/static_web jhashivam/project-01:nginx_image

docker push jhashivam/project-01:nginx_image

```

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-22.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-23.png)

> 16: stopping the running containers
```
docker ps 

docker stop  e038e086fbcd 296af5d7734b 41d2f6bca651 e36853beba7c

```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-24.png)

> 17: Delete Images
```
docker images

docker rmi 1ea775905bce 1ea775905bce e16366931005 3f73bcafca55 5f025950334a b80d2cac43e4 51086ed63d8c 216c552ea5ba feb5d9fea6a5 d4bd30aedcdc

```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-25.png)



### Assignment 2:

[Hello World Docker Image](https://hub.docker.com/_/hello-world)
Run Hello World Docker Image Locally.

```
docker pull hello-world

docker run hello-world
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-26.png)


### Assignment 3:
- Create a hello world fastapi application.
- Create a Dockerfile for your fastapi hello world application.
- Build Docker image using Docker file.
- Run docker image build in previous step.
- Push your Docker image to Docker Hub.

```
docker images

docker build -t fastapi-hello-world:0.1 .

docker run -p 8000:8000 --name my-api fastapi-hello-world:0.1

docker ps -l

docker tag fastapi-hello-world:0.1 jhashivam/project-01:fastapi_hello-world

docker push jhashivam/project-01:fastapi_hello-world
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-27.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-28.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-29.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-30.png)

### Assignment 4:
Automate Assignment below task using github action.
1. Build Docker Image 

[Artifacts_Repo](https://github.com/jhashivam/build-docker-Image-action))

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-31.png)

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-32.png)

2. Push Docker Image to Docker hub.

![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/dc-32.png)