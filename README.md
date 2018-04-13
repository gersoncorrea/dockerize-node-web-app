# Node.js Web App and Docker
---
Example of  how to get a Node.js app into a Docker container

#### Requirements
>- Node.js
>- Docker 
# Quickstart
---

## Building image

Go to directory that has your `Dockerfile` and run the following command to build the docker image.

`$ docker build -t <your-username>/node-web-app .`

Your image will now be listed by Docker:

``` bash
$ docker images

# Example
REPOSITORY                      TAG        ID              CREATED
node                            carbon     1934b0b038d1    5 days ago
<your username>/node-web-app    latest     d64d3505b0d2    1 minute ago
```

## Run the image

Run the image you previously built:

``` bash
$ docker run -p 49160:8080 -d <your-username>/node-web-app
```
## Test

To test your app, get the port of your app that Docker mapped:

``` bash
$ docker ps

# Example
ID            IMAGE                                COMMAND    ...   PORTS
ecce33b30ebf  <your username>/node-web-app:latest  npm start  ...   49160->8080
```

In the example above, Docker mapped the `8080` port inside of the container to the port `49160`

Now you can call your app using `curl`

More information in the followng place:

>- [Dockerizing a Node.js web app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)
