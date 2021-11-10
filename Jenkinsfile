pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Not Failing!"
                sh 'echo 1'
            }
            post {
                failure {
                    script {
                        env.FAILED_STAGE=env.STAGE_NAME
                    }
                }
            }
        }
        stage('Test') {
            steps { script {
                stage('Service A') {
                    stage('Unit Test') {
                        script {
                            echo "Failing!"
                            sh 'echo 1'
                        }
                        post {
                            failure {
                                script {
                                    env.FAILED_STAGE=env.STAGE_NAME
                                }
                            }
                        }
                    }
                }
            }}
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
