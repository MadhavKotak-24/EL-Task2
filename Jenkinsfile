pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'docker run --rm -v $PWD:/app -w /app node:20 npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'docker run --rm -v $PWD:/app -w /app node:20 npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t nodejs-demo-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop nodejs-demo-app || true
                docker rm nodejs-demo-app || true

                docker run -d \
                --name nodejs-demo-app \
                -p 3000:3000 \
                nodejs-demo-app:latest
                '''
            }
        }
    }
}