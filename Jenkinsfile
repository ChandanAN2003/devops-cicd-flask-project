pipeline {
    agent any

    stages {

        stage('Clone Repository') {
    steps {
        git branch: 'main', url: 'https://github.com/ChandanAN2003/devops-cicd-flask-project.git'
    }
}

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t chandan202003/devops-flask:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                bat 'docker push chandan202003/devops-flask:latest'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f kubernetes/'
            }
        }

    }
}