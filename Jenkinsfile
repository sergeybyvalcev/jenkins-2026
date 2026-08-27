pipeline {
    agent { 
        label '1c' 
        }

    environment {
        envString = 'true'
    }

    post {
        always {
            allure includeProperties: false, jdk: '', results: [[path: 'out/syntax-check/allure']]
            junit stdioRetention: '', testResults: 'out/syntax-check/junit/junit.xml'
            }
        failure { 
            bat 'echo failure' 
            }
        success { 
            bat 'echo success' 
            }
    }

    stages {
        stage('stage_1') {
            steps {
                bat 'echo Message from steps'
                //bat 'echo envString = ${envString}'
            }
        }
        stage("Build test base") {
            steps {                
                bat "chcp 65001\n vrunner init-dev"                
            }
        }
    }
}
