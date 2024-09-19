pipeline {
    agent any
    tools {
        maven "maven"
    }
    stages {
        stage('Clean up') {
            steps {
                deleteDir()
            }
        }
        stage('Clone repo') {
            steps {
                bat "git clone https://github.com/lilisrv/tp3.git" // Remplacez par sh si vous êtes sur Linux
            }
        }
        stage('Generate backend image') {
            steps {
                dir("tp3/backend") { // Assurez-vous que ce chemin est correct
                    bat "mvn clean install" // Remplacez par sh si vous êtes sur Linux
                    bat "docker build -t backend ." // Remplacez par sh si vous êtes sur Linux
                }
            }
        }
        stage('Run docker compose') {
            steps {
                dir("tp3/backend") { // Assurez-vous que ce chemin est correct
                    bat "docker-compose up -d" // Remplacez par sh si vous êtes sur Linux
                }
            }
        }
    }
}
