pipeline {
  agent {
    node {
      label 'agent slave'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'Build step'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing'
      }
    }

  }
}