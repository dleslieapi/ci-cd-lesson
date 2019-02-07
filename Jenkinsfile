pipeline {
  environment {
    registry = "dleslieapi/learning"
    registryCredential = 'dockerhub'
	dockerImage = ''
  }
  agent any
  stages {
    stage('Building image') {
      steps{
        script {
			def dockerImage = docker.build registry + ":$BUILD_NUMBER"
			
        }
      }
    }
	stage('Deploy image') {
		steps {
			script {
				docker.withRegistry('', registryCredential) {
					dockerImage.push()
				}
			}
		}
	}
  }
}