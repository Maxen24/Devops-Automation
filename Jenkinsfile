pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t java-backend-app .'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'docker run -p 8080:8080 java-backend-app'
                }
            }
        }
    }
}
