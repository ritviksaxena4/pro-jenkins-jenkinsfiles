pipeline {
    agent any

    stages {
        stage('git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/ritviksaxena4/pro-app-code-repo.git'
            }
        }
        stage('sleep 5') {
            steps {
                sh 'sleep 5'
            }
        }
        stage('list all the files') {
            steps {
                sh 'ls'
            }
        }
        stage('Building the application using maven') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('sleep_5') {
            steps {
                sh 'sleep 5'
            }
        }
        stage('docker_build') {
            steps {
                sh 'docker build -t devops-project:latest1 .'
            }
        }
        stage('logging to the ECR') {
            steps {
                sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 761018861517.dkr.ecr.us-east-1.amazonaws.com'
            }
        }
        stage('tagging the image for ECR') {
            steps {
                sh 'docker tag devops-project:latest1 761018861517.dkr.ecr.us-east-1.amazonaws.com/devops-project:latest1'
            }
        }
        stage('Push the image for ECR') {
            steps {
                sh 'docker push 761018861517.dkr.ecr.us-east-1.amazonaws.com/devops-project:latest1'
            }
        }
    }
}
