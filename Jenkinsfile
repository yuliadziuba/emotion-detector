pipeline {
    agent any
    stages {
        stage('Install Python & pip') {
            steps {
                sh '''
                apt-get update
                apt-get install -y python3 python3-pip
                '''
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Run tests') {
            steps {
                sh 'pytest tests'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t emotion-detector .'
            }
        }
        stage('Check sudo access') {
            steps {
                sh 'sudo whoami'
            }
        }
    }
}
