pipeline {
  agent any
  stages {
    stage('Copy artifact') {
      steps {
        sh '''echo $PWD

mkdir vit

chmod 777 vit'''
        copyArtifacts(projectName: 'freestyle', fingerprintArtifacts: true, filter: '*.jar', excludes: '*.log', target: 'vit')
        sh 'cat /vit/tobearchived.jar >> newarc.jar'
        archiveArtifacts '*.jar'
      }
    }

  }
}