pipeline {
    agent any
    environment {
        AWS_REGION = "ap-south-1"
        ECR_REGISTRY = "132.201.137.244" // Replace with your AWS Account ID if using standard ECR URL, or use aws ecr command
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
                    // Add your ECR login and push steps here
                    sh "echo 'Build and test successful!'"
                }
            }
        }
    }
}pipeline {
    agent any
    environment {
        AWS_REGION = "ap-south-1"
        ECR_REGISTRY = "132.201.137.244" // Replace with your AWS Account ID if using standard ECR URL, or use aws ecr command
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
                    // Add your ECR login and push steps here
                    sh "echo 'Build and test successful!'"
                }
            }
        }
    }
}
