pipeline{
    agent {
        docker {
            image "postman/newman"
            args "--entrypoint=''"
        }
        
    }

    stages{
        stage('verifier la version de newman'){
            steps{
                sh 'newman --version'
            }
        }

        stage('Install htmlextra'){
            sh "npm install newman-reporter-htmlextra"
        }

        stage('Test API'){
            steps{
                sh 'newman run collections/getUser.postman_collection.json --reporters htmlextra --reporter-htmlextra-export reports/api-test-report.html'
            }
        }
    }
    post{
        always {
            echo 'Archivage des rapports...'
            archiveArtifacts artifacts: 'reports/api-test-report.html', fingerprint: true
        }
    }
}