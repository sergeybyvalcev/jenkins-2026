pipeline {
    agent { 
        label '1c' 
        }

    environment {
        envString = 'true'
    }

    post {
        always {
            bat 'echo always'
            }
        failure { 
            bat 'echo failure' 
            }
        success { 
            bat 'echo success' 
            }
    }

    stages {
        // stage('stage_1') {
        //     steps {
        //         bat 'echo Message from steps'
        //         bat 'echo envString = ${envString}'
        //     }       
        // }
        stage('Build test base') {
            steps {
                bat 'chcp 65001\n vrunner init-dev --dt C:\\jenkins-exec\\dt\\1Cv8.dt --src C:\\repo\\jenkins-2026\\src\\cf'
                //bat 'echo envString = ${envString}'
            }       
        }

    }
}
