pipeline {
    agent any
    environment {
        AWS_REGION = "ap-south-1"
        AWS_ACCOUNT_ID = "132201137244" // Your AWS Account ID
        IMAGE_NAME = "image-regi"
        ECR_URL = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_REGION}.amazonaws.com"
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
                    sh """
                        aws ecr get-login-password --region ${AWS_REGION} | docker login --username AWS --password-stdin ${ECR_URL}
                        docker tag ${IMAGE_NAME}:latest ${ECR_URL}/${IMAGE_NAME}:latest
                        docker push ${ECR_URL}/${IMAGE_NAME}:latest
                    """
                }
            }
        }
    }
}
