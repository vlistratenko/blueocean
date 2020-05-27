pipeline {
  agent any
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

    stage('error') {
      steps {
        sh 'echo $PWD'
        copyArtifacts(projectName: 'blueocean', fingerprintArtifacts: true, filter: '*.jar', excludes: '*.log')
      }
    }

  }
}