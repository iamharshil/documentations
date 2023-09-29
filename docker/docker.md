<!-- After following Dockerfile -->
1. run `docker build -t hello-docker .` -t for tagging a name to our docker file and hello-docker is the tag for it, . for where our app is specified which is current directory in this case so . would help us here.
2. Once we're done with it docker does not store our image to specific folder and to view it execute this command in terminal `docker images` this shows all the docker images from your machine.
3. To run docker image in local machine execute `docker run tag-of-image`.
4. If I want I can publish this image to docker hub where everyone can use this image.