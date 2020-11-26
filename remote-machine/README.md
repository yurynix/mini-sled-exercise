Full explanation here:
https://nodejs.org/en/docs/guides/nodejs-docker-webapp/


# Quick start
Build the image
```
docker build -t remote-machine .
```

Run the container:
```
docker run -p 8080:8080 -d remote-machine
```

Now you can access the webserver:
```
curl http://localhost:8080/
```

And get `Hello world` as output