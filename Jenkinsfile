pipeline {
    agent {
        docker {
            image 'ubuntu:latest'
        }
    }
    environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
      }
    stages {
        stage('Test') {
            steps {
                sh 'id && hostname && ls && echo $AWS_ACCESS_KEY_ID && echo $AWS_SECRET_ACCESS_KEY'
            }
        }
    }
}
