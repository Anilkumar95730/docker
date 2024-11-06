# docker volume
When we create a container then by default volume will be created
Volume is a directory inside of our container
If we stop the container then also, we can access the volume
Volume can be created in one container
While creating the container only we can attach the created
volume to that container

# Different ways to create vloume
Automation
Manual
# different ways to map the volumes
Container  Container
Host  Container
# Automation process
1) yum install docker
2) systemctl start docker
3) Create Dockerfile ‘D’ is capital in Dockerfile
4) vi Dockerfile
   
           FROM ubuntu
           VOLUME ["/Anil"]
   FROM Specifies base image
VOLUME Give volume directory name
![Screenshot 2024-11-05 193648](https://github.com/user-attachments/assets/8d728262-8927-4443-abce-48d2f1ff0252)
Volume is created in container as shown in above image
To share that created volume for container to container we are
having the command
docker run -it --name new cont --privileged=true --volumes-from cont name image
# Manual process:
We need to create volume manually for the container by using
command
docker run -it --name new cont name -v/volume name
image name
Host to container
1. We can create the volume in host by using command
docker volume create volume name
2. To check the volumes in host
   docker volume ls
3. If we want to add files in host volume we need to inspect the volume, there you see the path 
To inspect the volume == docker volume inspect volume name
The path to add files ==var/lib/docker/volume/_data
To share the host volume to the container the command is
docker run -it --name new cont name --mountsource=volume name,destination=new volume name imagename
