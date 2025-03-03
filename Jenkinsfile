pipeline {
    agent {
        docker {
            image 'postman/newman'  
            args '--entrypoint=""'
        }
    }
    stages {
        stage('Check Newman Version') {
            steps {
                sh 'newman --version'
            }
        }
        stage('Run API Tests') {
            steps {
                // Exécution de Newman sans fichier d'environnement
                sh 'newman run collections/collection.json'
            }
        }
    }
}
