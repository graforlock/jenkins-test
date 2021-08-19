pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'exit 1'
            }
            
            post {
                failure {
                    sh "echo 'FAIL!'"   
                }
            }
        }
    }
    post {
        success {
            echo 'whole pipeline successful'
        }
        failure {
            echo 'pipeline failed, at least one step failed'
        }
    }
}
