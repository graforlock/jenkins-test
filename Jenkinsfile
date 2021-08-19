pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'exit 1'
            }
            
            failure {
                script {
                    sh "echo 'FAIL!'"   
                }
            }
        }
    }
}
