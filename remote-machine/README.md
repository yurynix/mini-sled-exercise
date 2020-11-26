Full explanation here:
https://nodejs.org/en/docs/guides/nodejs-docker-webapp/


# Quick start
To the purposses of this excersie, you can think of Docker as a lightweight "virtual machine".
docker image - the blueprint of the virtual machine
docker container - running instance of the docker image

We first build the image, put the application files on the image, then we create an image instance (container).

Build the image (all the commands should be performed on this directory)
```
docker build -t remote-machine .
```

Run the container:
```
docker run -v src:/ -p 8080:8080 -d remote-machine
```

Now you can access the webserver:
```
curl http://localhost:8080/
```

And get `Hello world` as output


In it's current state, once you changed the files in this directory, you need to repeat the process.

However, you might want to consider mounting the code as volume:
https://docs.docker.com/storage/volumes/#start-a-container-with-a-volume
