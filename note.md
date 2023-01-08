# Docker

## Configure Docker

* Prepare a Linux operating system computer  
Here we take the Debian system as an example

* Install Docker
Since we need Aliyun script to install Docker with one click  

we have to do these things: 
1) Use Aliyun mirror  
sudo vim /etc/apt/sources.list  
write the following
```bash
deb https://mirrors.aliyun.com/debian/ bullseye main non-free contrib
deb-src https://mirrors.aliyun.com/debian/ bullseye main non-free contrib
deb https://mirrors.aliyun.com/debian-security/ bullseye-security main
deb-src https://mirrors.aliyun.com/debian-security/ bullseye-security main
deb https://mirrors.aliyun.com/debian/ bullseye-updates main non-free contrib
deb-src https://mirrors.aliyun.com/debian/ bullseye-updates main non-free contrib
deb https://mirrors.aliyun.com/debian/ bullseye-backports main non-free contrib
deb-src https://mirrors.aliyun.com/debian/ bullseye-backports main non-free contrib
```

2) Install
```sh
sudo curl -fsSl https://get.docker.com | bash -s docker --mirror Aliyun
```

<font color='red'>If you don't have curl, you can try again after using this command:</font>
```sh
sudo apt-get update
sudo apt-get install curl
```

3) Accelerate with Aliyun image  
Go to Alibaba Cloud official website to find mirror acceleration  
Follow the above prompts to configure

## Basic use of docker  
* image
```sh
# This command is to search for mirror images, limit n means to limit the number of searched images to n
docker search [mirror name] [--limit n]

# Pull the image from DockerHub to the local
docker image pull [mirror name]

# Pull and run a mirror image, the command runs successfully and returns the container number
# -d  Indicates starting as a daemon
# -it Start in interactive mode and can be followed by a path to a terminal as an argument
# -p  Specify port mapping
# -P  port random mapping
docker run [-it] [mirror name]

# Show all local mirrors
docker image ls
docker images

# Display the id of the local mirror
docker image -q
```

* container
```sh
#  show running containers
docker ps

#  Stop the container from running
docker stop [container id]

#  Re-enter the running container by opening a new thread
docker exec -it [container id] [ternimal path]

# Re-enter the running container via the original thread
docker attach [container id]
```


