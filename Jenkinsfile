pipeline {
    agent { 
        label '1c' 
        }

    environment {
        envString = 'true'
    }

    post {
        always {
            allure includeProperties: false, jdk: '', resultPolicy: 'LEAVE_AS_IS', results: [[path: 'out/syntax-check/allure']]
            junit 'out/syntax-check/junit/junit.xml'   
        }
        failure { 
            bat 'echo failure' 
        }
        success { 
            bat 'echo success' 
        }
    }

    stages {      
        stage('Build test base') {
            steps {
                bat 'chcp 65001\n vrunner init-dev'                
            }       
        }
        stage('Syntax check') {
            steps {
                bat 'chcp 65001\n vrunner syntax-check'                
            }       
        }   

    }
}
