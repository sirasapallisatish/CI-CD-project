Name: SIRASAPALLI SATISH
TASK1: Setup Continuous Integration/Continuous Deployment (CI/CD) Pipeline
Objective:
Create a CI/CD pipeline to automate the build, test, and deployment processes for a web application using Jenkins, Docker, and GitHub/GitLab
1.Setup Jenkins Create  AWS ubuntu instance and name then Jenkins Server

2 .Connect to Jenkins server using Git bash

3. Update the apt repository
  Sudo  apt-get update

4 .Install jdk
  Sudo  apt-get install -y openjdk-11-jdk

5. Install git and maven
  Sudo  apt-get install -y git maven

6 .Downloaded Jenkins.war
  Wget https://get.jenkins.io/war-stable/2.361.3/jenkins.war
7. To start Jenkins 
  java -jar jenkins.war

8. To access Jenkins open browser
  public_ip_of_jenkinserver:8080


9. Unlock Jenkins by entering the password

10 .Click on Install suggested plugins (e.g. git, GitHub, Docker,  etc)

11 .Create admin user
Now Jenkins dashboard has been
Setup Version control
1.	I  set up a Git repository on GitHub to the web application code.
I have created a sample web application that is called a python application and then I pushed code into my GitHub repository.
Repo url: 
https://github.com/sirasapallisatish/CI-CD-project.git
2.	Now I  have Created Jenkins pipeline (Declarative Pipeline)
ChatGPT
Installing Docker on a Jenkins server typically involves a few steps. Here's a general guide:
1.	Prerequisites: Ensure that your Jenkins server meets the system requirements for Docker installation. This usually includes having a supported operating system (such as Linux) and meeting any hardware and software prerequisites specified by Docker.
2.	Update Package Repositories: Before installing Docker, it's a good practice to update your package repositories to ensure you're installing the latest versions of Docker.
bash
Copy code
sudo apt update
3.	Install Docker Dependencies: Depending on your system, you may need to install some dependencies before installing Docker. Common dependencies include apt-transport-https, ca-certificates, curl, software-properties-common, etc.
bash
Copy code
sudo apt install apt-transport-https ca-certificates curl software-properties-common
4.	Add Docker Repository: Docker provides official repositories for installing Docker on various Linux distributions. Add the Docker repository to your system's package manager.
bash
Copy code
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
5.	Install Docker: Once the Docker repository is added, install Docker CE (Community Edition) using your package manager.
bash
Copy code
sudo apt update
sudo apt install docker-ce
6.	Manage Docker as a Non-Root User (Optional): By default, Docker commands require root privileges. You may want to add your Jenkins user to the docker group to allow it to run Docker commands without sudo.
bash
Copy code
sudo usermod -aG docker jenkins
Replace jenkins with the username of your Jenkins user.
7.	Start and Enable Docker Service: Start the Docker service and enable it to start on boot.
bash
Copy code
sudo systemctl start docker
sudo systemctl enable docker
8.	Verify Docker Installation: Verify that Docker is installed and running correctly by running the following command:
bash
Copy code
docker --version


•	Here is the docker file
FROM node:14

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install application dependencies
RUN npm install

# Bundle app source
EXPOSE 3000
CMD [ "node", "app.js" ]
•	Build image using this command- docker build -t myimage .

