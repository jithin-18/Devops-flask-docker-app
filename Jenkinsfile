pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/jithin-18/devops-python-docker-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-devops-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop flask-container || true'
                sh 'docker rm flask-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-container flask-devops-app'
            }
        }

    }
}
