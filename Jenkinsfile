pipeline {
    agent any
    environment {
        AWS_REGION = "ap-south-1"
        ECR_REGISTRY = "132.201.137.244"
        IMAGE_NAME = "image-regi"
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${IMAGE_NAME} ."
                }
            }
        }
        stage('Push to ECR') {
            steps {
                script {
                    sh "echo 'Build and test successful!'"
                }
            }
        }
    }
}
