pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/lilisrv/tp3.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Run Background Process') {
            steps {
                // Remplacer nohup par start
                bat 'start /b java -jar target/app.jar'
            }
        }
    }
}
