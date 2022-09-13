[![philipomoigui](https://circleci.com/gh/philipomoigui/Operationalize-Machine-Learning.svg?style=svg)](https://app.circleci.com/pipelines/github/philipomoigui/Operationalize-Machine-Learning)

## Project Overview

In this project, I aim to take everything I learned in the Udacity cloud devops course to operationalize a Machine Learning Microservice API. 

I was given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests my ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

## What does this project do?

- Run a docker container
- Upload container into a public registry (hub.docker.com)
- Run the deployed application in a Kubernetes cluster
- Integrate with CircleCI for continuous integration

## Requirements
 - Python 3.7

## START HERE

### Step 0
- Fork this repo and clone it to your local workstation

### Step 1: Install dependencies
- Set up the environment by running `make setup`. This will create a virtual environment in your home directory called `.devops`
- Install dependencies by running `make install`

### Step 2: Setup and Run Docker container
- Install docker as described in the [link](https://docs.docker.com/engine/install/ubuntu/).
- Run the flask application on docker by calling `./run_docker.sh`
- Run `docker ps` to check if docker is running.
- Run `./make_prediction.sh` to make predictions

### Step 3: Upload to Docker Hub
- In the `upload_docker.sh` file, edit the dockerpath (line 9) and change the docker username to a personalized one.
- To upload to docker hub, run `./upload_docker.sh`

### Step 4: Setup and configure Kubernetes deployment
- Run `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`
- Run `sudo install minikube-linux-amd64 /usr/local/bin/minikube`
- Run `minikube start` to start minikube
- Run `kubectl get pods` to see which pods are running.
- Deploy the flask application to kubernetes by running `./run_kubernetes.sh`
- Run `./make_prediction.sh` to make prediction