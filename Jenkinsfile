pipeline {
    agent any

    stages {
        stage('Pull Source Code') {
            steps {
                git branch: 'main', url: 'https://github.com/salomohs9/e-voting-app.git'
            }
        }
            stage('Build Container Image') {
            steps {
                sh 'docker compose -f Docker-compose.yaml build'
            }
        }
                    stage('Deploy Container Apps') {
            steps {
                sh 'docker compose -f Docker-compose.yaml up -d'
            }
        }
                        stage('Push Image') {
            steps {
                sh 'docker compose -f Docker-compose.yaml push'
                
            }
        }
    }
}
