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
            def affectedPackages = readFile('affected-packages.json')
            build (job: "Jenkins-post-test", wait: false,
                   parameters: [string(name: 'AFFECTED_PACKAGES', defaultValue: affectedPackages)]))
        }
        failure {
            script {
                echo "pipeline failed on ${env.FAILED_STAGE}"
            }
        }
    }
}
