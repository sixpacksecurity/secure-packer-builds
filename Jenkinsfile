pipeline {
    agent {
        docker {
            image 'ubuntu:latest'
        }
    }
//    environment {
//        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
//        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
//      }
    stages {
        stage('Test') {
            steps {
                withAWS(credentials: 'aws-credentials', region: 'us-east-1') {
                    sh 'id && hostname && ls && echo $AWS_ACCESS_KEY_ID && echo $AWS_SECRET_ACCESS_KEY'
                }
            }
        }
    }
}
