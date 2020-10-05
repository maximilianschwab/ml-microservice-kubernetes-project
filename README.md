[![ml-microservice-kubernetes-project](https://circleci.com/gh/maximilianschwab/ml-microservice-kubernetes-project.svg?style=svg)](https://app.circleci.com/pipelines/github/maximilianschwab)

## Summary

The project is about a pre-trained, sklearn model that is used to predict the housing prices in Boston based on features like average rooms in a home, highway access and teacher-to-pupil ratio. The data which is used for the prediction is taken from Kaggle. A Flask app written in Python is used to serve the predictions via an API.

# Instructions

## Run this commands on your linux machine
* Install python 3.7 with the following command: `sudo apt install python3.7` 
* Switch to the project directory
* Execute `make setup`
* Execute `source ~/venv/.devops/bin/activate`
* Execute `make install`
* Execute `python app.py`
* Execute `./make_prediction.sh` to get a prediction result


## Runt the following scripts to build the Docker image and execute the corresponding container (you need to install Docker first!)
* Execute `./run_docker.sh`
* Execute `./make_prediction.sh` to make a prediction


## Running the Docker container inside a Kubernetes cluster (kubectl and minikube is required!)
* Execute `minikube start`
* Execute `./run_kubernetes.sh`
* Execute `./make_prediction.sh` to get a prediction result


# File Structure

├── README.md ==> the main documentation\
├── Dockerfile ==> This file is needed to create the docker image\
├── app.py  ==> Contains the Flask application\
├── make_prediction.sh ==> Contains JSON payload for get prediction form app.py\
├── Makefile ==> Needed for linting, setup and testing\
├── output_txt_files\
│   ├── docker_out.txt ==> terminal output after running the docker container and doing a prediction with make_prediction.sh \
│   └── kubernetes_out.txt ==> terminal output after running the kubernetes cluster and doing a prediction with make_prediction.sh \
├── requirements.txt ==> Python dependencies for the Flask application\
├── run_kubernetes.sh  ==> shell script to run the kubernetes cluster \
├── run_docker.sh ==> shell script to create the docker image and container\
└── upload_docker.sh  ==> script to upload the docker image to Dockerhub
