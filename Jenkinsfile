pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/ayushchahal44/docker-wordpress.git'
            }
        }
        stage('Build & Deploy') {
            steps {
                script {
                    bat 'docker-compose down || true'
                    bat 'docker-compose pull'
                    bat 'docker-compose up -d'
                }
            }
        }
    }
    post{
        always{
            echo 'Pipeline finished'
        }
    }
}