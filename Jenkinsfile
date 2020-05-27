pipeline {
  agent any
  stages {
    stage('Copy artifact') {
      steps {
        sh '''echo $PWD

mkdir vit

chmod 777 vit'''
        copyArtifacts(projectName: 'freestyle', fingerprintArtifacts: true, filter: '*.txt', excludes: '*.log', target: 'vit')
        sh 'cat $PWD/vit/tobearchived.txt >> newarc.txt'
        archiveArtifacts '*.jar, *.txt'
      }
    }

  }
}