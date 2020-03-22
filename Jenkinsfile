pipeline {
    agent {
        docker {
            image 'node:dubnium-alpine'
            args '-p 80:80'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Delivery') {
            steps {
                sh 'npm run start'
            }
        }
    }
}