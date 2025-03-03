pipeline {
    agent none

    stages {
        stage('intaller newman') {
            agent {
                docker {
                    image "postman/newman⁠"
                    args "--entrypoint=''"
                }   
            }
            
            steps {
                sh "newman run collections/getUser"
            }
        }
    }
}
