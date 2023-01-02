pipeline {
  agent none
  stages {
    stage('Say Hello') {
      agent { label 'nodejs-app' }
      steps {
        container('nodejs') {
          echo 'Hello World!'   
          sh 'java -version'
        }
      }
    }
  }
}
