# Docker

## Compute


```
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```

[Docker hub](https://hub.docker.com/) hosts a world of openly available docker images. 

In this tutorial, we'll pull the latest [ubuntu](https://hub.docker.com/_/ubuntu?tab=tags) image with:
```
$ docker pull ubuntu:latest
latest: Pulling from library/ubuntu
692c352adcf2: Pull complete                                                                                             97058a342707: Pull complete                                                                                             2821b8e766f4: Pull complete                                                                                             4e643cc37772: Pull complete                                                                                             Digest: sha256:55cd38b70425947db71112eb5dddfa3aa3e3ce307754a3df2269069d2278ce47
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest
```

Run an instance of this image, and get a shell to that running instance with
```
$ docker run -it ubuntu:latest bash
root@fe98a1ccbab0:/#
```

This is very similar to getting a shell to an Ubuntu VM on your machine.

Move around, and do some stuff in your shell. 
```
root@fe98a1ccbab0:/# echo hi
hi
root@fe98a1ccbab0:/# pwd
/
```


> Here, we start (`docker run`) an instance of the docker image `ubuntu:latest`, passing it a program to run (`bash`). We use the `-i` and the `-t` flags (combined into `-it`) to request an interactive shell to the container, allowing us to move around and do stuff in the `bash` session it opens for us.


> See `docker run` [docs](https://docs.docker.com/engine/reference/commandline/run/) or run `docker run --help` to see more info about these flags and arguments.


From the container, try creating a new `/app` directory at the root of your container's file system.
```
root@fe98a1ccbab0:/# ls
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@fe98a1ccbab0:/# mkdir /app
root@fe98a1ccbab0:/# cd /app
root@fe98a1ccbab0:/app# echo "hello from container" > message1.txt

root@fe98a1ccbab0:/app# cat message1.txt
hello from container
```

Exit with 
```
root@fe98a1ccbab0:/app# exit
exit
```

See your stopped container with
```
$ docker ps -a
CONTAINER ID        IMAGE                    COMMAND                  CREATED             STATUS                     PORTS                NAMES
fe98a1ccbab0        ubuntu                   "bash"                   2 minutes ago       Exited (0) 6 seconds ago                        crazy_mendeleev
```

Note the randomly generated `NAME` given to your container. 

_Restart_ your stopped container, using your `NAME` value instead
```
$ docker start crazy_mendeleev
crazy_mendeleev
```

And attach to the interactive shell with
```
$ docker attach crazy_mendeleev
```

Once in, re-visit `/app` and `cat` out your previous message
```
root@fe98a1ccbab0:/# pwd
/
root@fe98a1ccbab0:/# cd app/
root@fe98a1ccbab0:/app# ls
message1.txt
root@fe98a1ccbab0:/app# cat message1.txt
hello from container
```

Exit
```
root@fe98a1ccbab0:/app# exit
exit
```

and see the stopped container with
```
$ docker ps -a
CONTAINER ID        IMAGE                    COMMAND                  CREATED             STATUS                     PORTS                NAMES
fe98a1ccbab0        ubuntu                   "bash"                   5 minutes ago       Exited (0) 3 seconds ago                        crazy_mendeleev
```

Optionally remove it with:
```
$ docker rm crazy_mendeleev
crazy_mendeleev
```