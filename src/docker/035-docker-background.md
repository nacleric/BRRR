## Docker containers in the background

## `-d`

Sometimes, you'll want to run a docker process in the background. You may not care about being attached to it's `stdout`.

Use `-d`, or `--deamon` to run the process in the background, as a [daemon](https://en.wikipedia.org/wiki/Daemon_(computing)).

```
docker run -d -p 5678:5678 hashicorp/http-echo -text="hello from daemon webserver in a container"
```

See the container with 

```
$ docker run -d -p 5678:5678 hashicorp/http-echo -text="hello from daemon webserver in a container"
1524aa8131dab12cd0b9c7fd30e96ac39120c8e00469ac8e94ffdc8c3731e67e

$ docker ps
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS              PORTS                    NAMES
1524aa8131da        hashicorp/http-echo   "/http-echo '-text=h…"   5 seconds ago       Up 4 seconds        0.0.0.0:5678->5678/tcp   nifty_pasteur
```
> Note the first 3 characters of the `ID` column of your container. You can use this to identify your container, like when we fetch logs later.


It's pingable from a shell on your machine
```
$ curl localhost:5678
hello from daemon webserver in a container
```

See the container's logs with
```
$ docker logs 152 # Use first 3 chars of your container's ID
2020/07/07 08:20:39 Server is listening on :5678
2020/07/07 08:21:48 localhost:5678 172.17.0.1:43646 "GET / HTTP/1.1" 200 43 "curl/7.55.1" 7.3µs
```

