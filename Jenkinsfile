pipeline {
  agent any
  stages {
    stage('Install test tools') {
      steps {
        sh 'pip install molecule'
      }
    }
    stage('Test Redis') {
      steps {
        sh 'molecule --version'
      }
    }
  }
}
