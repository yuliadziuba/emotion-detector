pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run tests') {
            steps {
                sh 'pytest tests/'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t emotion-detector .'
            }
        }
    }
}