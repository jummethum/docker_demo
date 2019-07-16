pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }

  }
  stages {
    stage('deploy') {
      steps {
        sh 'python app.py'
      }
    }
  }
}