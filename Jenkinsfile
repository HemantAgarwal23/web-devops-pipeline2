pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t web-devops-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f web-container || exit 0'
                bat 'docker run -d -p 8081:80 --name web-container web-devops-app'
            }
        }
    }
}