# Docker Documentation
- Docker is container based tool which helps to prevent dependency conflicts and mismatches of their versions. 
- Setup
    1. Install docker by following (this)[https://docs.docker.com/desktop/ ] page.
    2. Make sure to follow prerequisites.

- Application setup
    1. Just for learning purpose create any basic application.
    2. I have created simple node application which prints "hello Docker.!!".
- Docker setup
    1. Create `Dockerfile` in root directory of your application.
    2. write the following lines into it
    ```
    FROM node:alpine
    COPY . ./app
    WORKDIR /app
    CMD node index.js
    ```
    3. Here `FROM node:alpine` is for which linux version or dependency we have to use for this application. I have used node:alpine since it has small size then other node dependency.
    4. `COPY . /app` here first . defined what to copy from our application in this case I have to copy all the files from my root of application so I put .(dot) there. `/app` is directory inside our docker image which defined where we have to store that image in our docker file.
    5. `CMD node index.js` I skipped WORKDIR because for understanding it you have to understand CMD first.
    6. CMD is basically your terminal command for run your application, maybe you have to install npm modules first and then run your application maybe you have to execute your application directly. Since we defined /app in our COPY path for docker image our application would be on `/app/index.js` dir inside docker image so command to run it would be `node /app/index.js` which is bit annoying.
    7. To solve that annoying problem we have WORKDIR which is prefix for our docker image so each time we set and CMD in our Dockerfile it will automatically pretend that there is /app/*our-command. any it will act like it.
- Run Docker
    - Once we're done with setup we will run `docker build -t hello-docker`. here -t represent tag and hello-docker is our tag name for this particular application to differentiate all apps from each other.