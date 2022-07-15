
[![Tamunoseimiebi](https://circleci.com/gh/Tamunoseimiebi/DevOps_Microservices.svg?style=svg)](https://app.circleci.com/Tamunoseimiebi/DevOps_Microservices)

## Project Overview
Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv and activate it by executing `python3 -m venv venv`
* Source the virtual environment: `source venv/bin/activate`
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./upload_docker.sh && ./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create a kubernetes secret to store the credentials of the private Docker registry
  ```bash
    kubectl create secret docker-registry regcred \
        --docker-server=https://index.docker.io/v1/ \
        --docker-username=<DOCKERHUB_USERNAME> \
        --docker-password=<DOCKERHUB_PASSWORD> \
        --docker-email=<DOCKER_EMAIL>
  ```
* Create Flask app in Container
* Run via kubectl

## Directory Structure

| Directory/File | Description |
| ---- | ----------- |
| `.circleci/config.yml` | CircleCI configuration |
| `model_data` | Trained model data for housing prices in Boston |
| `output_txt_files` | Docker and Kubernetes log output |
| `app.py` | REST Endpoint for predicting housing prices in Boston |
| `Dockerfile` | Dockerfile containing the application and its dependencies |
| `make_prediction.sh` | Calls prediction REST endpoint and simulates sample prediction |
| `Makefile` | Build file of the project |
| `requirements.txt` | Python requirements |
| `run_docker.sh` | Shell script for creating and running docker container |
| `run_kubernetes.sh` | Shell script to deploy docker container on Kubernetes cluster |
| `upload_docker.sh` | Shell script for uploading locally built docker image to dockerhub repository |
