pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t release .'
            }
        }
        stage('Delivery') {
            steps {
                sh 'docker run -d --restart=always -p 8000:80 release'
            }
        }
    }
}