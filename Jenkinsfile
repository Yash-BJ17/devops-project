pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Yash-BJ17/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f flask-container || true'
                sh 'docker run -d --name flask-container -p 5000:5000 flask-app'
            }
        }
    }
}
