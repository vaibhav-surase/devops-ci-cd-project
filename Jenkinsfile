pipeline {
    agent any

    environment {
        IMAGE_NAME = "vaibhavsurase/devops-app:latest"
    }

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/vaibhav-surase/devops-ci-cd-project.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push $IMAGE_NAME'
            }
        }

        stage('Deploy') {
            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}
