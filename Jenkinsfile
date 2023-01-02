pipeline {
  agent none
  environment {
    FAVORITE_COLOR = 'RED'
  }
  stages {
    stage('Pull Request') {
      when {
        beforeAgent true
        branch 'pr-*'
      }
      stages {
        stage('Build and Push Container Image') {
          steps {
            echo "FAVORITE_COLOR is $FAVORITE_COLOR"
            echo "TODO - Build and Push Container Image"
          }
        }
        stage('Test') {
          agent any
          options {
            timeout(time: 10, unit: 'SECONDS') 
          }
          environment {
            FAVORITE_COLOR = 'BLUE'
            SERVICE_CREDS = credentials('example-service-username-password')
          }          
          input {
            message "Should we continue with tests?"
          }
          steps {
            sh 'echo TODO - test $FAVORITE_COLOR with SERVICE_CREDS: username=$SERVICE_CREDS_USR password=$SERVICE_CREDS_PSW'
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
