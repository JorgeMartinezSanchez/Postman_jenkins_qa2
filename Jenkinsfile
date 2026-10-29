pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS' // Ensure this matches the exact name of your NodeJS installation in Jenkins global tool configuration
    }

    stages {
        stage('Install Dependencies') {
            steps {
                // Install Newman and the htmlextra reporter globally
                sh 'npm install -g newman newman-reporter-htmlextra'
            }
        }
        
        stage('Run newman') {
            steps {
                sh 'newman run GoRestCRUD.postman_collection.json -e GORest.postman_environment.json -r htmlextra --reporter-htmlextra-export reporte.html'
            }
        }
    }
}