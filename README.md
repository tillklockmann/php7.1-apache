## Docker for php development: an example with the php:7.1-apache image

This example only works on a debian OS. It assumes you have docker installed and know how to use the command line to execute the commands.

### usage

1. Clone this repository with
```
git clone <repo-name-url>
```
or download the zip file and unpack it. Cd into the directory.

2. build the image
```
docker build -t <container-image-name>  .
```
(Don't forget the dot at the end. It points to the current directory.)

3. run the container from the image
```
docker run -p 8080:80 -d -v "$PWD"/data:/var/www/html <container-image-name>
```
You have now a container with a runing apache server listing to localhost:8080. You should no be able to see the data/index.php output in your browser. And if you change the index.php file, you should also see the changes, because of ```-v "$PWD"/data:/var/www/html```. If you don't use ```"$PWD"``` you have to specify the absolute path.

---
#### **Useful docker commands**
list all docker containers including active ones
```
docker ps -a
```

enter a container by starting an interactive shell session
```
docker exec -it <container-name> /bin/bash
```

stop a container
```
docker stop <container-name>
```

delete a container
```
docker rm <container-name>
```

remove all containers and data
```
docker system prune
```
