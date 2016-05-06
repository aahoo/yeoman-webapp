# [yeoman + generator-webapp docker image](https://hub.docker.com/r/aahoo/yeoman-webapp/)

## Test Drive
1. run: `docker run -it --rm -p 9000:9000 aahoo/yeoman-webapp`
2. `mkdir -p my-project && cd $_`
3. `yo webappp`
4. `gulp serve`
5. open browser > "virtual machine IP":9000 (e.g. http://192.168.99.100:9000/)

## Regular Use
Mount a host directory to the container

### Need to do only for the first run
1. `mkdir -p my-project && cd $_`
2. `docker run -it -p 9000:9000 -v $(pwd):/home/yeoman/my-project --name wp  aahoo/yeoman-webapp`

> In windows, you may have to change `$(pwd)` to `/$(pwd)`

3. `yo webapp`
4. `gulp serve`
5. open browser > "virtual machine IP":9000 (e.g. http://192.168.99.100:9000/)

### Need to do for the following runs
0. `cd my-project`
1. `docker start -i yo`
2. `gulp serve`
3. open browser > "virtual machine IP":9000 (e.g. http://192.168.99.100:9000/)

## More info
This image is based on [aahoo/yeoman](https://hub.docker.com/r/aahoo/yeoman/). Since both of these images are "AUTOMATED BUILD", you can see their Dockerfiles to ensure that you don't compromise your project's security.
