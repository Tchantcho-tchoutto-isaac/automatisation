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
                // Utilisation du bon nom de fichier pour la collection
                sh 'newman run Collection1.postman_collection.json  --reporters junit --reporter-junit-export result.xml'
            }
        }
    }
}
