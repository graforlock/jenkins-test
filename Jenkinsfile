pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'exit 1'
            }
            
            post {
                failure {
                    script {
                        FAILED_STAGE=env.STAGE_NAME
                    }
                }
            }
        }
    }
    post {
        success {
            echo 'whole pipeline successful'
        }
        failure {
            echo 'pipeline failed on ${env.FAILED_STAGE}'
        }
    }
}
