pipeline {
    agent any

    environment {
        IMAGE_NAME = "anurag0626/docker-jenkins-demo:v1"
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Source Code Downloaded'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t docker-jenkins-demo:v1 .'
            }
        }

        stage('Tag Docker Image') {
            steps {
                sh 'docker tag docker-jenkins-demo:v1 $IMAGE_NAME'
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds',
                usernameVariable: 'USERNAME',
                passwordVariable: 'PASSWORD')]) {

                    sh 'echo $PASSWORD | docker login -u $USERNAME --password-stdin'

                }
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push $IMAGE_NAME'
            }
        }
    }
}