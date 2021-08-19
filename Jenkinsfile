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
}
