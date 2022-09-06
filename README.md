[![CircleCI](https://dl.circleci.com/status-badge/img/gh/patokenneth/Udacity-ML-Predictor-With-K8s/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/patokenneth/Udacity-ML-Predictor-With-K8s/tree/main)

## Project Overview

The crux of this project is to show how to operationalize a machine learning api, running it in multiple environments including Docker and Kubernetes. In a world where availability and scale is expected, we have demonstrated, using a condensed app, how we can make our applications to be robust and scalable. Following established architecture and frameworks used by the world's best like Google and Amazon, we serve a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on [the data source site](https://www.kaggle.com/c/boston-housing).

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

### Files and Uses
This projet contains a couple of shell scripts and .txt files to automate some frequently run commands and save results. The Dockerfile is the blueprint for building the docker image. The makefile is the organised way of running basic commands like setting up the virtual environment, installing dependencies and even linting the code. This helps in creating a truly reusable codebase. The app.py contains the source code and we use the run_docker.sh to run the project in docker containers while the run_kubernetes.sh runs it in a kubernetes cluster. The result of these two modes of running the application can be seen in the docker_out.txt and kubernetes_out.txt respectively. To trigger an actual prediction, we run the make_prediction.sh script. 
