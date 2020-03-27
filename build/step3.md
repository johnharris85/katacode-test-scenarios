### Run the Container

Now we've got a built image, let's run a container based on that image and test we can hit our webserver.

Use `docker run -it -p 8000:8000 my-image:v0.1`{{execute}} to run a container.

And let's break down the command:

- `docker run` - Tell Docker to _run_ a container
- `-it` - In interactive mode with a TTY
- `-p 8000:8000` - Forward port 8000 on our host to port 8000 inside the container
- `my-image:v0.1` - The image to run the container from (in this example, the one we built in the previous step)

Now the container is running, we can switch to the exposed port on our host and check out the response:

https://[[HOST_SUBDOMAIN]]-8000-[[KATACODA_HOST]].environments.katacoda.com/