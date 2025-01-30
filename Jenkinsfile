pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t devops-simulation .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run devops-simulation python -m pytest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f k8s-deployment.yaml'
            }
        }
    }
}