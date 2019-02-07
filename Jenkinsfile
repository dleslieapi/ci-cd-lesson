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
			def myImage = docker.build registry + ":$BUILD_NUMBER"
			
        }
      }
    }
	stage('Deploy image') {
		docker.withRegistry('', 'ZGxlc2xpZWFwaQ==:dGVzdGluZw==') {
			myImage.push()
		}
	}
  }
}