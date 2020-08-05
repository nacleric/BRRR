## Docker networking

Pull a simple hello webserver.

Ref: https://hub.docker.com/r/hashicorp/http-echo/

Pull
```
docker pull hashicorp/http-echo
```
We'll run this image, using [`--port`(docs)](https://docs.docker.com/engine/reference/commandline/run/#publish-or-expose-port--p---expose). Now, we are outfitting our running process (container) with some basic "networking". 

In this case, with `-p X:Y`, we are saying map the port within the container `Y` to port `X` on the host machine.

```
docker run -p 8080:5678 hashicorp/http-echo -text="hello from the webserver in a container"
```
> Here, we specify the image (`hashicorp/http-echo`) and some argument (`-text="..."`). Note that we didn't specify the _program_ we want to run, like we did with `docker run ubuntu:latest bash` in the previous example. This is because `hashicorp/http-echo` has defined an [`ENTRYPOINT`(docs)](https://docs.docker.com/engine/reference/builder/#entrypoint) for their image. When an `ENTRYPOINT` is defined, that is the default program invoked when the image is started, and the rest of the `docker run` command are passed as args/flags to that program.


In a new shell, you can see the webserver from the container is responding to your host machine's port 8080 (`localhost:8080`)

```
$ curl localhost:8080
hello from the webserver in a container
```

Exit (`Ctrl + C`) your webserver container.

Notice the webserver is stopped, and `localhost:8080` is no longer responding.
