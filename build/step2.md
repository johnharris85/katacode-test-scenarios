### Build the Image

Inside the `Dockerfile` you'll see a few instructions:

> FROM golang:1.13

This `FROM` instruction means we'll be using the `golang:1.13` image as a base to build upon.

> COPY main.go .

The `COPY` instruction allows us to copy a file from our local directory (`main.go`) into the built image in the current working directory (`.`).

> RUN go build -o /server

`RUN` allows us to specify steps that should be run _during_ the image build process. In this case, using the go runtime to build the `server` binary from our `main.go` program.

> CMD ["/server"]

Finally the `CMD` lets us specify which command should be run _by default_ (this can be overridden by other systems later on if desired) when a container is run from this image. In this case we specify our built `server` binary.

Let's build the image using `docker build -t my-image:v0.1 .`{{execute}}.

This command tells the Docker engine to `build` an image with the tag (`-t`) of `my-image:v0.1` with the Dockerfile located in the current working directory (`.`).
