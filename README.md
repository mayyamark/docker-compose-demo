# docker-compose-demo

## Step 1: Setup

1. Create a `app.py` file
2. Create a `requirements.txt` file

## Step 2: Create a Dockerfile

1. Build an image starting with the Python 3.7 image.
1. Set the working directory to /code.
1. Set environment variables used by the flask command.
1. Install gcc and other dependencies
1. Copy requirements.txt and install the Python dependencies.
1. Add metadata to the image to describe that the container is listening on port 5000
1. Copy the current directory . in the project to the workdir . in the image.
1. Set the default command for the container to flask run.

## Step 3: Define services in a Compose file🔗

1. Web service

The web service uses an image that’s built from the Dockerfile in the current directory. It then binds the container and the host machine to the exposed port, 5000. This example service uses the default port for the Flask web server, 5000.

2. Redis service

The redis service uses a public Redis image pulled from the Docker Hub registry.

## Step 4: Build and run the app with Compose

1. From the project directory, start up the application by running `docker-compose up`.
1. Enter `http://localhost:5000/` in a browser to see the application running
1. Switch to another terminal window, and type docker image ls to list local images. You can inspect images with docker inspect <tag or id>.
1. Stop the application, either by running `docker-compose down --volumes`
