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
    }
}

