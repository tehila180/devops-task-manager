pipeline {
    agent any

    environment {
        AWS_REGION = "us-east-1"
        ECR_REGISTRY = "028210901910.dkr.ecr.us-east-1.amazonaws.com"
        BACKEND_IMAGE = "task-manager-backend"
        FRONTEND_IMAGE = "task-manager-frontend"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Backend') {
            steps {
                dir('backend') {
                    bat 'docker build -t backend .'
                }
            }
        }

        stage('Build Frontend') {
            steps {
                dir('frontend') {
                    bat 'docker build -t frontend .'
                }
            }
        }

        stage('AWS Login to ECR') {
            steps {
                bat '''
                aws ecr get-login-password --region %AWS_REGION% ^
                | docker login --username AWS --password-stdin %ECR_REGISTRY%
                '''
            }
        }

        stage('Tag Images') {
            steps {
                bat '''
                docker tag backend:latest %ECR_REGISTRY%/%BACKEND_IMAGE%:latest
                docker tag frontend:latest %ECR_REGISTRY%/%FRONTEND_IMAGE%:latest
                '''
            }
        }

        stage('Push to ECR') {
            steps {
                bat '''
                docker push %ECR_REGISTRY%/%BACKEND_IMAGE%:latest
                docker push %ECR_REGISTRY%/%FRONTEND_IMAGE%:latest
                '''
            }
        }

        stage('Verify') {
            steps {
                bat 'docker images'
            }
        }
    }
}