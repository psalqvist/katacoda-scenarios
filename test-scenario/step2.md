## Build docker image and push to Docker Hub

The second step will be to build a docker image and push this to Docker Hub.

First, check that docker is installed by running `docker -v`.

Then, craete a file called `dockerfile` inside our directory `kubernetes-tutorial` with the following content:

```
FROM node:latest

WORKDIR /usr/src/app

COPY package.json ./

RUN npm install

COPY . .

EXPOSE 3001
CMD [ "node", "index.js" ]
```

Here we set the working directory, copy the dependencies, install dependencies, copy our index.js, select port and finally run the command `node index.js`.

Now it is time to craete the docker image by running `docker build -t <Docker Hub username>/kubernetes-tutorial`. It is important to use your exact **Docker Hub username**, otherwise we won't be able to push the image to Docker Hub.





Next, we will craete a dockerfile and push it to Docker Hub.