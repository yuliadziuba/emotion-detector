pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
                sh 'git clone https://github.com/yuliadziuba/emotion-detector.git repo'
            }
        }

        stage('Install Python & pip') {
            steps {
                dir('repo') {
                    sh '''
                    apt-get update
                    apt-get install -y python3 python3-pip
                    '''
                }
            }
        }

        stage('Install dependencies') {
            steps {
                dir('repo') {
                    sh 'pip3 install -r requirements.txt'
                }
            }
        }

        stage('Run tests') {
            steps {
                dir('repo') {
                    sh 'pytest tests'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                dir('repo') {
                    sh 'docker build -t emotion-detector .'
                }
            }
        }

        stage('Build') {
            steps {
                dir('repo') {
                    sh 'echo "Add your build command here"'
                }
            }
        }
    }
}

