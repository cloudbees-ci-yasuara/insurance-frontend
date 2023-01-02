pipeline {
  agent none
  stages {
    stage('Pull Request') {
      when {
        beforeAgent true
        branch 'pr-*'
      }
      stages {
        stage('Build and Push Container Image') {
          steps {
            echo "TODO - Build and Push Container Image"
          }
        }
        stage('Test') {
          agent {
            kubernetes {
              yamlFile 'nodejs-pod.yaml'
            }
          }
          steps {
            container('nodejs') {
              echo 'Hello World!'   
              sh 'node --version'
            }
          }
        }
      }
    }
    stage('Main Branch Stages') {
      when {
        beforeAgent true
        branch 'main'
      }
      stages {
        stage('Push Image to Prod Registry') {
          steps {
            echo "TODO - push image"
          }
        }
        stage('Deploy') {
          steps {
            echo "TODO - deploy"
          }
        }
      }
    }
  }
}
