## TASK1-INTERN CAREER ##

## **Description**: **Create a CI/CD pipeline to automate the build, test, and deployment processes for a web application using Jenkins, Docker, and GitHub/GitLab.** ##

# **Title**: Setup Continuous Integration/Continuous Deployment (CI/CD) Pipeline  #

## **Introduction**: ##
Create a CI/CD pipeline to automate the build, test, and deployment processes for a web application using Jenkins, Docker, and GitHub/GitLab.

## **System Requirements**: ##

### 1 **Setup Jenkins**: ###

==================**JENKINS INSTALLATION**===============================

a. Install Jenkins on a cloud server.

Install JDK 8
$ sudo apt update
$ sudo install openjdk-8-jdk -y

Install JDK11 on BuildMachine:
$ apt install openjdk-11-jdk -y


## Add the repository key to the system: ##
=======================================

$ sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key


## Append the Debian package repository: ##
==========================================

$  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null

## Install Jenkins Package ##
=============================

$ sudo apt-get update
$ sudo apt-get install fontconfig openjdk-17-jre
$ sudo apt-get install jenkins

## Status of Jenkins ##
======================

$ systemctl status jenkins | systemctl start jenkins


b. Configure Jenkins with necessary plugins for Git integration, pipeline support (e.g., Pipeline, PipelineGitHub, Pipeline Docker), and any additional tools required for your project.

c. Create a new Jenkins pipeline project.

### 2. Configure Version Control: ###
========================================

a. Set up a Git repository on GitHub or GitLab to host the web application code.
b. Create a sample web application (e.g., HTML/CSS/JavaScript, Node.js, Python Flask, etc.) and push it to the Git repository.

### 3. Create Jenkins Pipeline: ###
========================================

a. Write a Jenkinsfile (declarative or scripted pipeline) to define the CI/CD stages:
i. Build Stage: Pull the code from the Git repository, compile/build the application.
ii. Test Stage: Run automated tests (unit tests, integration tests, etc.) on the built application.
iii. Deploy Stage: Package the application into a Docker container, push the container to Docker Hub or a private registry, and deploy it to a test/staging environment.

### 4. Configure Docker: ###
================================

a. Install Docker on the Jenkins server or a separate Docker host.

==================**DOCKER INSTALLATION**========================


sudo apt update -y
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" -y
$ apt-cache policy docker-ce -y
$ sudo apt install docker-ce -y
$ sudo systemctl status docker | systemctl start docker
$ sudo chmod 777 /var/run/docker.sock
$ which docker
$ docker info




b. Create a Dockerfile to define the container environment and dependencies for your web application.
c. Set up Docker Hub or a private Docker registry for container storage.






