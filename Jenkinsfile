pipeline {
agent any

stages {

    stage('Clone') {
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

    stage('Docker Compose Up') {
        steps {
            bat 'docker compose up -d'
        }
    }

    stage('Running Containers') {
        steps {
            bat 'docker ps'
        }
    }

}

}
