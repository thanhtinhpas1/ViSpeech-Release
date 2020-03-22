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
                sh 'docker rm -f release'
                sh 'docker run --name=release -d --restart=always -p 8000:8000 release'
            }
        }
    }
}