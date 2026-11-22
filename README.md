# Jenkins CI/CD Pipeline Practice

## Project Overview

This project demonstrates the fundamentals of Jenkins CI/CD using a Jenkins Pipeline.

The pipeline is defined using a `Jenkinsfile` and stored in a GitHub repository. Jenkins retrieves the pipeline code from GitHub and executes the defined stages.

The purpose of this project is to understand how Jenkins automates software delivery and how Pipeline as Code works.

## Technologies Used

- Jenkins
- Docker
- Git
- GitHub
- Linux
- Jenkins Pipeline
- Groovy-based Declarative Pipeline

## Jenkins Setup

Jenkins was installed and configured locally using Docker.

A Docker volume was used to persist Jenkins data.

```bash
docker volume create jenkins_home

docker run -d \
  --name jenkins \
  -p 8080:8080 \
  -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  jenkins/jenkins:lts
```

Access Jenkins through:

http://localhost:8080

## Pipeline Stages

The Jenkins pipeline contains the following stages:

1. **Checkout** – Retrieves the source code from the GitHub repository.
2. **Build** – Executes the build stage.
3. **Test** – Runs the testing stage.
4. **Deploy** – Executes the deployment stage.

## Jenkinsfile

The pipeline is defined in a `Jenkinsfile` stored in the root directory of the GitHub repository.

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
            }
        }
    }
}
```

## What I Learned

- Installing and running Jenkins using Docker
- Creating Jenkins Freestyle jobs
- Creating Jenkins Pipeline jobs
- Writing a Declarative Jenkinsfile
- Understanding pipeline stages and steps
- Configuring Jenkins to retrieve a Jenkinsfile from GitHub
- Understanding Pipeline as Code
- Troubleshooting Jenkins pipeline configuration and SCM checkout errors

## Project Goal

To build a strong foundation in Jenkins and CI/CD automation, and gradually extend this pipeline with:

- GitHub webhook integration
- Automated Docker image build
- Docker image push to Docker Hub
- Automated application deployment
- Jenkins credentials management

## Author

Dhanya M C

GitHub: [dhanyamc97](https://github.com/dhanyamc97)
