pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t devops-simulation-app .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run devops-simulation-app python -m pytest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f k8s-deployment.yaml'
            }
        }
    }
}