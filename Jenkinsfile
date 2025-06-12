pipeline {
    agent any
    stages {
        stage('Installer les dépendances') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Exécuter le script') {
            steps {
                bat 'python scraper.py'
            }
        }
        stage('Archiver le résultat') {
            steps {
                archiveArtifacts artifacts: 'data.csv', fingerprint: true
            }
        }
    }
}
