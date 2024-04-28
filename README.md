## TASK1-INTERN CAREER ##

## **Description** ##: Create a CI/CD pipeline to automate the build, test, and deployment processes for a web application using Jenkins, Docker, and GitHub/GitLab.

# **Title**: Setup Continuous Integration/Continuous Deployment (CI/CD) Pipeline  #

## **Introduction**: ##
Create a CI/CD pipeline to automate the build, test, and deployment processes for a web application using Jenkins, Docker, and GitHub/GitLab.


![interncareer](https://github.com/ankumpetvimala/TASK-INTERN-CAREER/assets/155473936/5f0e4024-3ee9-4f0b-afd0-0277482aac08)

## **System Requirements**: ##

### 1 Launch an EC2 Instance : ###

Log in to your AWS console.

Navigate to EC2.

Click "Launch Instance."

Choose the "t2.micro" instance type.

Configure other settings (VPC, security groups, key pair, etc.).

Security groups Port - 8080 for Jenkins , Port - 3000 for Docker 

Launch the instance.

### 2 **Setup Jenkins**: ###

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

### 3. Acess Jenkins ###

Open a web browser and navigate to [Jenkins login Page](http://3.80.133.177:8080/) 

https://ec2-public-ip:8080/

Retrieve the initial admin password from the Jenkins server:

### sudo cat /var/lib/jenkins/secrets/initialAdminPassword ###


b. Configure Jenkins with necessary plugins for Git integration, pipeline support (e.g., Pipeline, PipelineGitHub, Pipeline Docker), and any additional tools required for your project.

**Install Plugins**

In Jenkins, go to "Manage Jenkins" > "Manage Plugins."

Install necessary plugins (e.g., Pipeline, GitHub, Docker).

c. Create a new Jenkins pipeline project.

**Create New Jenkins Pipeline**

Create a new Jenkins job.

Select "Pipeline" as the job type.

Write your Groovy script in the pipeline configuration.


### 4. Configure Version Control: ###
========================================

a. Set up a Git repository on GitHub or GitLab to host the web application code.

The first step in setting up a CI/CD pipeline is to store your source code in a repository. This will allow you to manage and track changes to your code over time.

If you haven't already, create a repository for your web application in a Git-based repository management platform, such as GitHub or GitLab. Make sure to push your latest code changes to the repository.

gitclone https://github.com/ankumpetvimala/TASK-INTERN-CAREER.git


b. Create a sample web application (e.g., HTML/CSS/JavaScript, Node.js, Python Flask, etc.) and push it to the Git repository.

### 5. Create Jenkins Pipeline: ###
========================================

a. Write a Jenkinsfile (declarative or scripted pipeline) to define the CI/CD stages:

i. Build Stage: Pull the code from the Git repository, compile/build the application.

ii. Test Stage: Run automated tests (unit tests, integration tests, etc.) on the built application.

iii. Deploy Stage: Package the application into a Docker container, push the container to Docker Hub or a private registry, and deploy it to a test/staging environment.

### 6. Configure Docker: ###
================================

a. Install Docker on the Jenkins server or a separate Docker host.

==================**DOCKER INSTALLATION**========================

$ sudo apt update -y

$ sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" -y

$ apt-cache policy docker-ce -y

$ sudo apt install docker-ce -y

$ sudo systemctl status docker | systemctl start docker

$ sudo chmod 777 /var/run/docker.sock

$ which docker

$ docker info

b. Create a Dockerfile to define the container environment and dependencies for your web application.

c. Set up Docker Hub or a private Docker registry for container storage.

### 7. Integrate Jenkins with GitHub/GitLab: ###

**GitHub Integration:**

Go to your GitHub repository.

Under "Settings," select "Developer settings."

Generate a classic token and copy it.

a. Configure Jenkins to trigger the pipeline automatically on code commits/merges to the Git repository.

**Configure Jenkins with GitHub Credentials:**

In Jenkins, go to "Manage Jenkins" > "Configure System."

Add your GitHub username and paste the token as the password.

**DockerHub Integration:**

Go to DockerHub.

Generate an access token.

**Configure DockerHub in Jenkins:**

In Jenkins, go to "Manage Jenkins" > "Configure System."

Add your DockerHub username and paste the token.

b. Add webhook or webhook-like functionality to receive notifications from the version control system.

**Adding Webhook in Github**

Go to your GitHub repository.

Under "Settings," select "Webhooks."

Click on "Add webhook."

Set the payload URL to your Jenkins server's URL followed by /github-webhook/.

Select the events you want to trigger the webhook (e.g., Push events).

Optionally, you can set up a secret and configure Jenkins to validate the webhook payload using this secret.

Save your webhook configuration.

### 8. Test and Validate: ###

a. Run the Jenkins pipeline manually or trigger it through a code commit to the Git repository.

b. Monitor the CI/CD pipeline execution in Jenkins, check for build/test failures, and troubleshoot any issues

### Conclusion ###

With a CI/CD pipeline in place, you can ensure that changes to your web application are integrated and deployed quickly and with high quality. By automating the build, test, and deployment process, you can reduce the risk of bugs and downtime and improve the overall stability of your application.




