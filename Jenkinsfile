pipeline {
  agent {
    node {
      label 'agent'
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

    stage('') {
      steps {
        sh './create_file.sh'
      }
    }

  }
}