pipeline {
    agent {
        docker {
            image 'postman/newman'  
            args '--entrypoint=""'
        }
    }
    stages {
        stage('Install Newman Reporter htmlextra') {
            steps {
                // Installation de htmlextra reporter si nécessaire
                sh 'npm install -g newman-reporter-htmlextra'
            }
        }
        stage('Check Newman Version') {
            steps {
                sh 'newman --version'
            }
        }
        stage('Run API Tests') {
            steps {
                // Exécution de Newman avec le reporter htmlextra
                sh 'newman run Collection1.postman_collection.json --reporters htmlextra --reporter-htmlextra-export result.html'
            }
        }
    }
}
