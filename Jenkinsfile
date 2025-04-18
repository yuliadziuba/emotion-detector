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
        stage('Clone repo') {
            steps {
                sh 'git clone https://github.com/yuliadziuba/emotion-detector.git repo'
                dir('repo') {
                    sh 'ls -la'
                }
            }
        }
        stage('Build') {
            steps {
                dir('repo') {
                    sh 'your-build-command-here'
                }
            }
        }
    }
}
