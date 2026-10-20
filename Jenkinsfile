pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Laravel project checked out from GitHub'
                sh 'ls -la'
            }
        }

        stage('Build') {
            steps {
                sh 'docker compose build app'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker compose up -d'
            }
        }

        stage('Verify') {
            steps {
                sh 'curl -f http://localhost:8000'
            }
        }
    }
}
