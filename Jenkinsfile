pipeline {
    agent {
        docker {
            image 'hashicorp/packer:latest'
            args "--entrypoint=''"
        }
    }
    environment {
        AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
        PACKER_CACHE_DIR = "${env.WORKSPACE_TMP}/.packer.d/packer_cache"
        PACKER_CONFIG_DIR = "${env.WORKSPACE_TMP}/.packer.d"
        PACKER_HOME_DIR = "${env.WORKSPACE_TMP}/.packer.d"
        PACKER_PLUGIN_PATH = "${env.WORKSPACE_TMP}/.packer.d/plugins"
        TMPDIR = "${env.WORKSPACE_TMP}"
      }
    stages {
        stage('Initialize and Build') {
            steps {
                sh 'pwd && ls && packer init . && packer build .'
            }
        }
    }
}
