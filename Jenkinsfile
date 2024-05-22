pipeline {
    agent any
    
    environment {
        // Define environment variables if needed
        DOCKER_IMAGE = 'flaskapiimage:latest'
        CONTAINER_NAME = 'flaskApiContainer'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/flask']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/subhajit-007/devops_assignment.git']])
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    sh 'docker build -t ${DOCKER_IMAGE} .'
                }
            }
        }
        
        stage('Deploy Docker Container') {
            steps {
                script {
                    // Stop and remove any existing container
                    sh 'docker stop ${CONTAINER_NAME} || true'
                    sh 'docker rm ${CONTAINER_NAME} || true'

                    // Run the Docker container
                    sh 'docker run -d -p 8000:8000 --name ${CONTAINER_NAME} ${DOCKER_IMAGE}'
                }
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline execution completed.'
        }
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline execution failed.'
        }
    }
}
