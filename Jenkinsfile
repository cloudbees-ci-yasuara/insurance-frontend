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
          environment {
            FAVORITE_COLOR = 'BLUE'
          }
          steps {
            echo "TODO - test $FAVORITE_COLOR"
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
