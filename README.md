# Machine Learning with Microservices

[![GitHub](https://circleci.com/gh/aanorbel/ud-nd9991-DevOps_Microservices.svg?style=svg)](https://app.circleci.com/pipelines/github/aanorbel/ud-nd9991-DevOps_Microservices)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API.

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:

* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

## Files structure

```sh
.
├── .circleci
│   └── config.yml #Contains the configurations needed for the pipeline on circleci
├── Dockerfile
├── Makefile # Includes instructions on environment setup and lint tests
├── README.md
├── app.py # Is the python flask app
├── make_prediction.sh # Makes prediction for housing prices
├── model_data
│   ├── boston_housing_prediction.joblib
│   └── housing.csv
├── output_txt_files
│   ├── docker_out.txt
│   └── kubernetes_out.txt
├── requirements.txt #  Contains all the dependencies
├── run_docker.sh # Builds the docker image and run it on the specified port
├── run_kubernetes.sh # Runs the flask app via kubernetes
└── upload_docker.sh # Uploads the docker image to the specify docker repository

```

---

## Setup the Environment

* Create a virtualenv and activate it
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. As standalone application:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Upload docker image: `./upload_docker.sh`
4. Run in Kubernetes:  `./run_kubernetes.sh`
5. Make predictions: `./make_prediction.sh`
6. Access the logs: `kubectl logs ml-api-app`

### Kubernetes Steps

* To set up Docker use following tutorial: `https://docs.docker.com/desktop/`
(if using windows use Chocolatey and run `choco install docker` in elevated shell)
* To set up Kubernetes use following tutorial: `https://kubernetes.io/docs/tasks/tools/install-kubectl/`
(if using windows use Chocolatey and run `choco install kubectl` in elevated shell)
* To set up Minikube use following tutorial: `https://kubernetes.io/docs/tasks/tools/install-minikube/`
(if using windows use Chocolatey and run `choco install minicube` in elevated shell)
* (In the shell) run `minikube start` to create a Kubernetes cluster
* (In the shell) run `kubectl config view` to ensure the cluster is running properly
* (In the shell) run `kubectl config view` to ensure the cluster is running properly
* Run (tn the shell) run `minikube stop` to stop a Kubernetes cluster
* Finally run (tn the shell) run `minikube delete` to delete a Kubernetes cluster