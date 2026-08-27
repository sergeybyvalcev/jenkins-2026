pipeline {
    agent { 
        label '1c' 
        }

    environment {
        envString = 'true'
    }

    post {
        always { bat 'echo always' }
        failure { bat 'echo failure' }
        success { bat 'echo success' }
    }

    stages {
        stage('stage_1') {
            steps {
                bat 'echo Message from steps'
                bat 'echo envString = ${envString}'
            }
        }
    }
}
