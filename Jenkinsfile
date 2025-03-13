pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/gaganphadke/CC_TA_jenkins']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES2UG22CS196-1'
                sh 'g++ new.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
           echo 'error Pipeline failed'
        }
    }
}
