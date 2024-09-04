pipeline {
    agent any
    
    stages {
        stage("Code") {
            steps {
                echo "Cloning the code"
                git url: "https://github.com/swwapnil777/jenkins-declarative-pipeline.git", branch: "master"
            }
        }
        
        stage("Build") {
            steps {
                echo "Building the code"
                sh "docker build -t notes-app:latest ."
            }
        }
        
        stage("Push To Docker Hub") {
            steps {
                echo "Pushing the image to Docker Hub"
                withCredentials([usernamePassword(credentialsId: "dockerhub", passwordVariable: "DOCKER_HUB_PASS", usernameVariable: "DOCKER_HUB_USER")]) {
                    sh "docker login -u ${DOCKER_HUB_USER} -p ${DOCKER_HUB_PASS}"
                    sh "docker tag notes-app ${DOCKER_HUB_USER}/notes-app:latest"
                    sh "docker push ${DOCKER_HUB_USER}/notes-app:latest"
                }
            }
        }
        
        stage("Cleanup") {
            steps {
                echo "Cleaning up old Docker images"
                sh "docker image prune -f"
            }
        }
        
        stage("Deploy") {
            steps {
                echo "Deploying the container"
                sh "docker compose down --remove-orphans && docker compose up -d"
            }
        }
    }
}
