pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/mahichouhan18/jenkins-docker-cicd-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t jenkins-docker-cicd .'
            }
        }

        stage('Deploy Container') {
            steps {
                bat 'docker rm -f jenkins-cicd-app || exit 0'
                bat 'docker run -d --name jenkins-cicd-app -p 8081:80 jenkins-docker-cicd'
            }
        }
    }
}