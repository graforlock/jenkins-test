pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Not Failing!"
                sh 'echo 1'
            }
        }
        
        stage('Build Job') {
            steps {
                script {
                    def affectedPackages = readFile('affected-packages.json')
                    build (job: "Jenkins-post-test", wait: false,
                       parameters: [string(name: 'AFFECTED_PACKAGES', value: affectedPackages)])  
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
                echo "pipeline failed on ${env.FAILED_STAGE}"
            }
        }
    }
}
