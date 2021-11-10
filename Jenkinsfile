pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Not Failing!"
                sh 'echo 1'
            }
        }
    }
    post {
        success {
            echo 'whole pipeline successful'
            build (job: "Jenkins-post-test", wait: false)
        }
        failure {
            script {
                echo "pipeline failed on ${env.FAILED_STAGE}"
            }
        }
    }
}
