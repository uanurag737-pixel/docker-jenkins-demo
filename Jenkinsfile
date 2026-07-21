pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source Code Downloaded Successfully'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Docker Application'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Application'
                sh 'date'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment Completed Successfully'
            }
        }

    }
}