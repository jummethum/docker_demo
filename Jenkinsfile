pipeline {
    agent { dockerfile true }
    stages {
        stage('deplox') {
            steps {
                sh 'pyhton app.py'
            }
        }
    }
}