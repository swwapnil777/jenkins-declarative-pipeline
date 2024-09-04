
# Jenkins Declarative CI/CD Pipeline
![CICD](https://github.com/user-attachments/assets/63bacf8a-96b3-4839-9aa9-8aa29ef20d4d)

Welcome to the Jenkins Declarative CI/CD Pipeline repository! This project demonstrates how to set up a CI/CD pipeline using Jenkins for Docker image building, pushing to Docker Hub, and deploying to an EC2 instance.

## Project Overview



This repository contains a Jenkins Declarative Pipeline that automates the following processes:

1. **Code Cloning**: Clones the source code from a GitHub repository.
2. **Build**: Builds a Docker image from the source code.
3. **Push**: Pushes the Docker image to Docker Hub.
4. **Deploy**: Deploys the Docker image to an EC2 instance using Docker Compose.

## Pipeline Stages

- **Code**: 
  - Clones the code from GitHub.
  
- **Build**: 
  - Builds the Docker image with the tag `notes-app:latest`.

- **Push To Docker Hub**: 
  - Logs in to Docker Hub and pushes the image to the repository.

- **Deploy**: 
  - Uses Docker Compose to deploy the container to the EC2 instance.

## Technologies Used

- **Jenkins**: For Continuous Integration and Continuous Deployment (CI/CD).
- **Docker**: For containerization.
- **EC2**: For hosting and deploying the application.
- **GitHub**: For source code management.
- **Docker Hub**: For storing Docker images.

## Getting Started

To use this pipeline, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/swwapnil777/jenkins-declarative-pipeline.git
   cd jenkins-declarative-pipeline
   ```

2. **Configure Jenkins**:
   - Set up a Jenkins job and configure the pipeline using the `Jenkinsfile` in this repository.
   - Add necessary credentials for Docker Hub in Jenkins.

3. **Docker Setup**:
   - Ensure Docker is installed on your EC2 instance and the Docker daemon is running.

4. **Deployment**:
   - Configure Docker Compose on the EC2 instance to match the deployment requirements.

## Repository Contents

- `Jenkinsfile`: Contains the Declarative Pipeline definition.
- `docker-compose.yml`: Docker Compose configuration file for deployment.
- `README.md`: This file.
