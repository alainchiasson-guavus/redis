pipeline {
  agent {
    docker { image 'alainchiasson/docker-molecule' }
  }
  stages {
    stage('Install test tools') {
      steps {
        sh 'command -v molecule || pip install molecule'
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
