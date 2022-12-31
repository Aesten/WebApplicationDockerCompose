# WebApplicationDockerCompose

To use docker-compose, you just need to clone this repository and use 2 commands.

- Step 1: Create the images

~~~shell
docker-compose build
~~~

- Step 2: Run the web application

~~~shell
docker-compose up
~~~

If you want to stop the running instance, use:

~~~shell
docker-compose stop
~~~

The environment variables and ports can be changed in the file docker-compose.yml.
Some default values are set so if you run docker-compose without changing anything it should immediately work.
