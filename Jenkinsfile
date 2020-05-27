pipeline {
  agent any
  stages {
    stage('Copy artifact') {
      steps {
        sh 'echo $PWD'
        copyArtifacts(projectName: 'freestyle', fingerprintArtifacts: true, filter: '*.jar', excludes: '*.log')
      }
    }

  }
}