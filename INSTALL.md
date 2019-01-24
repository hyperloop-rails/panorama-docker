You can find the installation instructions [here](https://hyperloop-rails.github.io/panorama/docs/docker).

You can also find it as belows:

### Pull and run the docker image 
* Login to you docker hub account and pull the [docker image](https://cloud.docker.com/repository/docker/panorama/chrome):
```
$ docker pull panorama/chrome:fifth
```

* If you are using Mac, make sure [XQuartz](https://www.xquartz.org) is installed and opened before running the start script.

* Copy the following into a script file (e.g., `start.sh`), and login to the docker image by running this script:
```
#!/bin/bash
IP=$(ifconfig en0 | grep inet | awk '$1=="inet" {print $2}')
docker run -it \
-e DISPLAY=$IP:0 \
--privileged \
-p 127.0.0.1:3000:3000 \
-v "${HOME}/.Xauthority:/root/.Xauthority" \
-v /tmp/.X11-unix:/tmp/.X11-unix \
panorama/chrome:fifth
```

