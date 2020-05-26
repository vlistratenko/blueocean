pipeline {
  agent none
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
        sh 'touch artifact.jar'
        archiveArtifacts(artifacts: 'artifact.jar', fingerprint: true, onlyIfSuccessful: true)
      }
    }

  }
}