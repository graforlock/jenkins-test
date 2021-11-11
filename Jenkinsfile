pipeline {
    agent any

    parameters {
        string(defaultValue: "123", description: 'This is a parameter', name: 'PARAM')
    }

    stages {
        stage('Start'){
            steps{
                    build job: 'Jenkins-post-test', wait: false, parameters: [string(name: 'B', value: String.valueOf(PARAM))]
            }
        }
    }
}
