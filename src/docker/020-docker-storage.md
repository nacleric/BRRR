## Docker Storage (mount volume to host)


Often, a program might accumulate important data over time. 

If the program crashes and is lost (like `docker rm <CONTAINER_NAME>` in the previous section), we might want to make sure accumulated application data (`/app`) is not lost with it.

_Or_, one might want to starta newer version of a program, but have it access the same application data an earlier instance of the program generated.

In this next section, we will run a docker program, but persist data in the `/app` dir of the container to your host VM's file system.

This way, application data is preserved and available outside the ephermeral nature of a container, and _it's_ VM-like filesystem.

### [`-v` (docs)](https://docs.docker.com/engine/reference/run/#volume-shared-filesystems)

Start a `bash` session, but with the container's `/app` path mounted to a new `./host` directory in your current working directory.

Windows (command prompt)
```
mkdir host
docker run -it -v %cd%/host:/app ubuntu:latest bash
```

Linux (bash)
```
mkdir -p host
docker run -it -v $(pwd)/host:/app ubuntu:latest bash
```


`cd` and echo something to a text file there
```
cd /app
echo "hello from container" > message1.txt
```

Exit
```
exit
```

and see your output persisted to your host's file system.

```
$ ls host
message1.txt

$ cat host/message1.txt
hello from container
```

Now, we can stop, totally remove an "application" (a container)
```
$ docker ps -a
CONTAINER ID        IMAGE                    COMMAND                  CREATED             STATUS                         PORTS                    NAMES
1524aa8131da        hashicorp/http-echo      "/http-echo '-text=h…"   57 minutes ago      Up 57 minutes                  0.0.0.0:5678->5678/tcp   nifty_pasteur
$ docker stop 152
152
$ docker rm 152
152
```

and know that any "application data" is persisted to our local `./host` directory!

We can always `run` a new instance of our program, mounted (`-v`) to the same data directory, and the program can continue with any relevant application data within its reach.

We have "persisted storage" for our application! 