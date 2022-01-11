
# Minimal, Local, Containerized Jupyter Lab with Docker


# Getting Started

0. Install `git` and clone this repo.
1. Install Docker for your system.
2. "Build" the container for this project. This downloads all the pre-requisite software to run this container.
3. Run the following command.

```
docker run \
	-v $(pwd):/home/jovyan \
	-p 8888:8888 \
	-e JUPYTER_ENABLE_LAB=yes AUTHENTICATE_VIA_JUPYTER="mytoken"
	docktest
```