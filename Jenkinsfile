def FAILED_STAGE

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
                        echo 'FAILED!'
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
            script {
                echo 'pipeline failed on ${FAILED_STAGE}'
            }
        }
    }
}
