pipeline {
    agent any

    stages {
        stage('Installer les dépendances') {
            steps {
                bat '"C:\\Python311\\python.exe" -m pip install --upgrade pip'
                bat '"C:\\Python311\\python.exe" -m pip install -r requirements.txt'
            }
        }

        stage('Exécuter le script') {
            steps {
                bat '"C:\\Python311\\python.exe" scraper.py'
            }
        }

        stage('Archiver le résultat') {
            steps {
                archiveArtifacts artifacts: 'data.csv', fingerprint: true
            }
        }
    }
}
