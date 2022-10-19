# Docker & Docker Hub


### Assignment 1:

Demonstrate minimum 15 basic docker command with explanation and screenshot.

> 1: Check docker version

```
docker version
```
![image](https://github.com/jhashivam/Industry_Ready_projects/blob/main/Docker/images/doc_01.png)

> 2: Run a Container
`If we want to download a docker image and run container on it then we run docker run <image_name> syntax. In below syntax we are downloading debian image and starting container over it by using docker run debian command as shown below. This command will pull the latest image from repository if not already available in the system and then it will create and start the container using that image.`

```
docker run debian
```

> 3: Check all running Containers


> 4: Create a Container


> 5: Start and attach STDIN to a Container


> 6: List all the docker images


> 7: Check the status of all Containers


> 8: Remove all unused Images


> 9: Run Container in Detach Mode


> 10: Stop a Container


> 11: Remove a Container


> 12: Access a Container


> 13: Start a docker Container


> 14: Restart a docker Container


> 15: List all the docker network Details


> 16: Check Complete Docker Information


> 17: Search a Docker Image


> 18: Create a Docker Volume


> 19: List all the Docker Volume


> 20: Kill a Container


> 21: Download a docker Image


> 22: Save a Image to a Tar Archive


> 23: Check Docker Stats


> 24: forcefully delete a docker Image


> 25  Load Image from a Tar File


> 26: Check docker disk Usage


> 27: Login to Docker Hub


> 28: Log out from Docker Registry


> 29: Create a new Image from a Container's Changes


> 30: Inspect the Changes of Container Files and Directories


> 31: Pause all the processes within a Container


> 32: Update a Container's CPU-Shares


> 33: Unpause all the processes within a Container


> 34: Tag an Image By ID


> 35: Check the Logs of a Container


> 36: Push an Image to Dockerhub


> 37: Rename a Container


```
docker images
```


### Assignment 2:

[Hello World Docker Image](https://hub.docker.com/_/hello-world)
Run Hello World Docker Image Locally.


### Assignment 3:
Create a hello world fastapi application.
Create a Dockerfile for your fastapi hello world application.
Build Docker image using Docker file.
Run docker image build in previous step.
Push your Docker image to Docker Hub.


### Assignment 4:
Automate Assignment below task using github action.
1. Build Docker Image 
2. Push Docker Image to Docker hub.