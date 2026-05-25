pipeline {
agent any
stages {
 stage('Clone Repository') {
 steps {
 git 'https://github.com/your-username/web-devops-pipeline.git'
 }
 }
 stage('Build Docker Image') {
 steps {
 bat 'docker build -t web-devops-app .'
 }
 }
 stage('Run Docker Container') {
 steps {
    bat 'docker run -d -p 8080:80 --name web-container web-devops-app'
 }
 }
}
}