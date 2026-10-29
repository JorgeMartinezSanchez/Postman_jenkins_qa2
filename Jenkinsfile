pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage('Run newman') {
            steps {
                sh 'newman run GoRestCRUD.postman_collection.json -e GORest.postman_environment.json -r htmlextra --reporter-htmlextra-export reporte.html'
            }
        }
    }
}