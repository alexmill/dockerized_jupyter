
# Minimal, Local, Containerized Jupyter Lab with Docker


# Getting Started

0. Install Docker for your system.
1. Install `git` and clone this repo.
2. Navigate into the repo and "Build" the container for this project. This downloads all the pre-requisite software to run this container.
```bash
cd ./dockerized_jupyter 
docker build -t jupyter_lab_docker .
```
3. Get the `$IMAGE_ID` of the Docker image you just created:
```bash
IMAGE_ID=$(docker image ls | grep jupyter_lab_docker | awk '{print $3}')
```
4. "Run" the generated Docker image and launch Jupyter with the following command:
```bash
docker run \
  --volume $(pwd):/home/jovyan \
  --publish 8888:8888 \
  --env JUPYTER_ENABLE_LAB="yes" \
  $IMAGE_ID
```
