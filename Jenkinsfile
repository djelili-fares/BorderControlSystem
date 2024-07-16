pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/votreutilisateur/BorderControlSystem.git'
            }
        }

        stage('Build') {
            steps {
                sh 'make'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Vous pouvez ajouter des commandes de test ici
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'main', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Build and Tests succeeded!'
        }
        failure {
            echo 'Build or Tests failed!'
        }
    }
}
