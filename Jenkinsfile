pipeline {
    agent any

    environment {
        IMAGE_NAME = "madhavkotak/nodejs-demo-app"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $nodejs-demo-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop node-app || true
                docker rm node-app || true

                docker run -d \
                  --name node-app \
                  -p 3000:3000 \
                  $nodejs-demo-app:latest
                '''
            }
        }
    }
}