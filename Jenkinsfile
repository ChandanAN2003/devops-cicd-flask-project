pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/ChandanAN2003/devops-cicd-flask-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t chandan202003/devops-flask:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push chandan202003/devops-flask:latest'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f kubernetes/'
            }
        }

    }
}