## TASK1-INTERN CAREER ##

## **Description**: **Create a CI/CD pipeline to automate the build, test, and deployment processes for a web application using Jenkins, Docker, and GitHub/GitLab.** ##

# **Title**: Setup Continuous Integration/Continuous Deployment (CI/CD) Pipeline  #

**Introduction**:
Create a CI/CD pipeline to automate the build, test, and deployment processes for a web application using Jenkins, Docker, and GitHub/GitLab.

**System Requirements**:

1 **Setup Jenkins**:

==================**Installing Jenkins**===============================

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


Append the Debian package repository:
==========================================

$  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null

Install Jenkins Package
=============================

$ sudo apt-get update
$ sudo apt-get install fontconfig openjdk-17-jre
$ sudo apt-get install jenkins

Status of Jenkins
======================

$ systemctl status jenkins | systemctl start jenkins


b. Configure Jenkins with necessary plugins for Git integration, pipeline support (e.g., Pipeline, PipelineGitHub, Pipeline Docker), and any additional tools required for your project.

c. Create a new Jenkins pipeline project.


