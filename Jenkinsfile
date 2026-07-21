pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source Code Downloaded'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker --version'
                sh 'docker build -t docker-jenkins-demo:v1 .'
            }
        }

        stage('Verify Image') {
            steps {
                sh 'docker images'
            }
        }
    }
}