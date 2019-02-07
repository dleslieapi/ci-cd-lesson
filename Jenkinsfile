pipeline {
  environment {
    registry = "dleslieapi/learning"
    registryCredential = 'dockerhub'
  }
  agent any
  stages {
    stage('Building image and push') {
      steps{
        script {
		  docker login -u dleslieapi -p testing
          def customImage = docker.build registry + ":$BUILD_NUMBER"
		  customImage.push()
        }
      }
    }
  }
}