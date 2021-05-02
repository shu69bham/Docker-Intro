# Docker-Intro

This is a basic demonstration of using docker on local windows machine

Please refer to - https://www.youtube.com/watch?v=WcQ3-M4-jik by IAmTimCorey for more detailed videos.

# Installing WSL(Windows Subsystem for Linux)

Go to the following link - https://docs.microsoft.com/en-us/windows/wsl/install-win10 and run commands in step1 and step3 on cmd(run as administrator)

# Basic commands

### `docker images`
Shows list of all images.

### `docker image history`
Shows history of all the subimages used in the image.

### `docker build -t MyImageName:TagName .`
Build a new image based on the configuration in the dockerfile(Don't forget the dot in the end of the command).

Eg=> docker build -t second-image:1.0.1 .

### `docker run --name MyContainerName -p InputPort:OutputDockerPort ImageNameWithTag`
Creates a new container with the images passed. Maps the request coming on InputPorts to OutputDockerPort.

Eg=> docker run --name my-new-container -p 8080:80 second-image:1.0.1

In the above command we have mapped 8080 port of our local machine with the port number 80 of docker(on which our http server runs in docker).
Note : Use -d to run the container in the background even if the VSCode is closed

### `docker ps -a`
Shows list of all container. -a in the end makes sure all the containers(even non running) are listed.

### `docker stop ContainerName`
Stops a container. ContainerName can be small enough to help identify the container uniquely.

### `docker start ContainerName`
Starts a container. ContainerName can be small enough to help identify the container uniquely.
