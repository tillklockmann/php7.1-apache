## using docker for php development: an example with the php:7.1-apache image
### usage

1. clone this repository with
```
git clone <repo-name-url>
```
and cd into the cloned directory <repo-name>.

2. build the image
```
docker build -t <container-image-name>  .
```
(Don't forget the dot at the end. It points to the current directory.)

3. run the container from the image
```
docker run -p 8080:80 -d -v "$PWD"/data:/var/www/html <container-image-name>
```
This will run a apache server listing to localhost:8080. You should no be able to see the data/index.php output in your browser. And if you change the index.php file, you should also see the changes, because of ```-v "$PWD"/data:/var/www/html```.

