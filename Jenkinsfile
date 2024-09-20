pipeline {
    agent any

    tools {
        // Spécifie l'outil Git configuré dans Jenkins
        git 'Default Git'  // Assurez-vous que ce nom correspond à l'installation que vous avez définie dans Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone le dépôt SCM (Source Code Management) 
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Exécute la commande Maven pour compiler le projet
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Exécute les tests
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Déploiement éventuel (adapter selon votre environnement)
                echo 'Deploying application...'
            }
        }
    }

    post {
        always {
            // Archive les logs ou les résultats des tests après chaque build
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
