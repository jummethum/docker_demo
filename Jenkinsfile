pipeline {
  node {
    checkout scm
    def customImage = docker.build("friendlyhello:${env.BUILD_ID}")

  }
  stages {
    stage('deploy') {
      steps {
        customImage.withRun('-p 4000:80') {
		}
      }
    }
  }
}