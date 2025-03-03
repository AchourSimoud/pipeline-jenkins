pipeline {
    agent none

    stages {
        stage('intaller newman') {
            agent {
                docker "postman/newman⁠"
                
            }
            
            steps {
                sh "newman run collections/collecion"
            }
        }
    }
}
