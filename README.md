# Docker-Compose-Project-for-CI-CD-Pipeline
This project provides a Docker Compose setup for running SonarQube and Jenkins, which can be used as part of a CI/CD pipeline to improve code quality and automate parts of the software development process.
## What is Docker Compose?
Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you define a multi-container application in a single file, then spin up your application in a single command. Compose makes it easy to orchestrate and manage your containers, networks, and volumes.

## Services
This Docker Compose project includes two services:

## SonarQube Service
SonarQube is an open-source platform for continuous inspection of code quality. It provides detailed reports on code coverage, bugs, vulnerabilities, and code smells.
The `sonarqub`e service is created using the `sonarqube:lts` image. It exposes the SonarQube web interface on port `9000` and is connected to the `mynetwork` network.

The service also uses the following volumes:

`SonarQube_data`: stores the SonarQube data files. <br>

`SonarQube_extensions`: stores the SonarQube extensions. <br>

`SonarQube_logs`: stores the SonarQube logs. <br>

These volumes are created automatically and can be accessed from the host machine. <br>


## Jenkins Service
Jenkins is an open-source automation server that helps to automate parts of the software development process. It can be used to build, test, and deploy software.
The `jenkins` service is created using the jenkins/jenkins:lts image. It exposes the Jenkins web interface on port `8081` and is connected to the `mynetwork` network.

The service also uses the following volumes:

`jenkins_home`: stores the Jenkins home directory. <br>

`/var/run/docker.sock`: allows Jenkins to communicate with the Docker daemon. <br>

`/usr/local/bin/docker`: allows Jenkins to run Docker commands. <br>

The `privileged` and `user` options are set to run the Jenkins container with root permissions. <br>

## Getting Started
To get started with this project, make sure you have Docker and Docker Compose installed on your machine.

### 1. Clone this repository: <br>
  #### `git clone https://github.com/abbashussainz/Docker-Compose-Project-for-CI-CD-Pipeline.git`

### 1. Clone this repository: <br>
  #### `cd Docker-Compose-Project-for-CI-CD-Pipeline`

### 2. Start the services:
  #### `docker-compose up -d`

## Access the services:

SonarQube: http://localhost:9000 <br>
Jenkins: http://localhost:8081

## Notes
The `volumes` section is used to persist data for the SonarQube and Jenkins services.
The `networks` section is used to create a custom network for the SonarQube and Jenkins services to communicate on.
