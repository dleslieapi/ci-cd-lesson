pipeline {
  environment {
    registry = "dleslieapi/learning"
    registryCredential = 'dockerhub'
  }
  agent any
  stages {
    stage('Building image') {
      steps{
        script {
          def customImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
   stage('Push container to registry') {
      steps {
        customImage.push()
      }
    }
  }
}