# springboot-docker
A test of Docker with Spring Boot, following https://spring.io/guides/gs/spring-boot-docker/

## Install Docker

  1. First of all, install [Docker](https://docs.docker.com/installation) and check it is running
  2. If not started, start the service running

      $ sudo service docker start

## Build and test

Now, you can build and test as usual

    $ mvn package && java -jar target/gs-spring-boot-docker-0.1.0.jar

## Docker

### Run

Use Docker to deploy and start a contained image

  * __Note__: if you are using __boot2docker__ you need to run it first before you do anything with the Docker command line or with the build tools (it runs a daemon process that handles the work for you in a virtual machine).
  * __Note__: Before proceeding with the following steps (which use Docker’s CLI tools), make sure Docker is properly running by typing ``docker ps``. If you get an error message, something may not be set up correctly. Using a Mac? Add ``$(boot2docker shellinit 2> /dev/null)`` to the bottom of your ``.bash_profile`` (or similar env-setting configuration file) and refresh your shell to ensure proper environment variables are configured.

Build docker image and run locally

    $ mvn package docker:build
    $ docker run -p 8080:8080 -t $USER/gs-spring-boot-docker

### Stop

First get the container ID
  
    $ docker ps

Then, stop the container with this command:

    $ docker stop ${ID} # Replace ${ID} with the container ID

