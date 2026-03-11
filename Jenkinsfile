pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                credentialsId: '91381e4f-159a-43f6-afa2-f3b91b795c7d',
                url: 'https://github.com/Kashyapraz/devops-website.git'
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
