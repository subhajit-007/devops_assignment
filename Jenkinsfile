pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/python']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/subhajit-007/devops_assignment.git']])
            }
        }
        stage('Setup Python') {
            steps {
                // Install Python and virtual environment
                script {
                    if (!fileExists("venv/bin/activate")) {
                        sh 'python3 -m venv venv'
                    }
                    sh '. venv/bin/activate'
                }
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install dependencies
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }
        
        stage('Build') {
            steps {
                git branch: 'python', url: 'https://github.com/subhajit-007/devops_assignment.git'
                sh '. venv/bin/activate && python3 main.py'
            }
        }
        
        stage('Test') {
            steps {
                sh '. venv/bin/activate && pip install pytest && python3 -m pytest'
            }
        }
    }
    
    post {
        always {
            // Clean up virtual environment
            sh 'rm -rf venv'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }

}
