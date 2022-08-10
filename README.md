# devops-codewizard

## Requirements

1. Download and install [Docker](https://docs.docker.com/get-docker/) and [Docker-Compose](https://docs.docker.com/compose/install/)
2. [Windows Git Bash](https://gitforwindows.org/)
3. Install [Choco](https://chocolatey.org/install)
4. Install [jq](https://stedolan.github.io/jq/) and [Helm](https://helm.sh/docs/intro/install/)
   ```bash
   choco install -y jq kubernetes-helm
   ```
   
1. Install [minikube](https://community.chocolatey.org/packages/Minikube/) according to [this tutorial](https://github.com/unfor19/kubernetes-localdev#kubernetes-hands-on-self-paced-course-)
   ```bash
   choco install -y minikube --version 1.21.0
   ```
   
2. (Optional) [Visual Studio Code](https://code.visualstudio.com/)

## Exercise 1

1. Start Jenkins server locally
   ```bash
   docker-compose -f exercise1/docker-compose.yaml up -d --build
   ```
   
1. Login to Jenkins server by navigating to http://localhost:8081
1. Run this command to get the initial admin password
   ```bash
   cat jenkins_home/secrets/initialAdminPassword
   ```
   
1. Select "Suggested Plugins to install"
2. Install CSAC with Manage Jenkins > Configuration as Code plugin

## Exercise 2

Following this tutorial - https://docs.bitnami.com/tutorials/create-openldap-server-kubernetes/

1. Start a Kubernetes cluster locally with minikube
   ```bash
   minikube start --driver=docker --kubernetes-version=v1.21.2
   ```