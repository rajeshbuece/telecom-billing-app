pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/rajeshbuece/telecom-billing-app.git'
            }
        }
        stage('Build Docker Images') {
            steps {
                sh 'docker build -t rajeshbueece/telecom-customer-service:latest ./customer-service'
                sh 'docker build -t rajeshbuece/telecom-billing-service:latest ./billing-service'
                sh 'docker build -t rajeshbuece/telecom-network-usage-service:latest ./network-usage-service'
            }
        }
        stage('Push Docker Images') {
            steps {
                sh 'docker push rajeshbuece/telecom-customer-service:latest'
                sh 'docker push rajeshbuece/telecom-billing-service:latest'
                sh 'docker push rajeshbuece/telecom-network-usage-service:latest'
            }
        }
    }
}
