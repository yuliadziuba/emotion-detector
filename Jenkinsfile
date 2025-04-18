pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Run tests') {
            steps {
                bat 'pytest tests/'
            }
        }
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t emotion-detector .'
            }
        }
    }
}