pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Kashyapraz/devops-website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-website .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }

    }
}
