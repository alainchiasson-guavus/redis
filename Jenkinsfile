pipeline {
  agent any
  stages {
    stage('Install test tools') {
      steps {
        sh 'pip install molecule'
      }
    }
    stage('Validate molecule') {
      steps {
        sh 'molecule --version'
      }
    }
    stage('Create test Machines') {
      steps {
        sh 'molecule create'
      }
    }
    stage('Converge Machines') {
      steps {
        sh 'molecule converge'
      }
    }
    stage('Run test') {
      steps {
        sh 'molecule verify'
      }
    }
    stage('Test idempotency') {
      steps {
        sh 'molecule idempotency'
      }
    }
  }
}
