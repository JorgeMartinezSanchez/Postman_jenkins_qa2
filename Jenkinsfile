pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install -g newman newman-reporter-htmlextra'
            }
        }
        
        stage('Run newman') {
            steps {
                // Add --suppress-exit-code or || true to prevent build failure on assertion errors
                sh 'newman run GoRestCRUD.postman_collection.json -e GORest.postman_environment.json -r htmlextra --reporter-htmlextra-export reporte.html --suppress-exit-code'
            }
        }
    }
    
    post {
        always {
            // Archive the HTML report in Jenkins
            archiveArtifacts artifacts: 'reporte.html', allowEmptyArchive: true
        }
    }
}