pipeline {
  agent none
  stages {
    stage('Copy artifact') {
      parallel {
        stage('Copy artifact') {
          agent {
            node {
              label 'master'
            }

          }
          steps {
            sh '''echo $PWD

mkdir vit

chmod 777 vit'''
            copyArtifacts(projectName: 'freestyle', fingerprintArtifacts: true, filter: '*.txt', excludes: '*.log', target: 'vit')
            sh 'cat $PWD/vit/tobearchived.txt >> newarc.txt'
            archiveArtifacts '*.jar, *.txt'
          }
        }

        stage('stash') {
          agent {
            node {
              label 'agent'
            }

          }
          steps {
            sh '''touch /root.txt
cd /
echo aaa >> root.txt
touch root2.txt'''
            stash(name: 'root', allowEmpty: true, includes: '*.txt')
          }
        }

      }
    }

    stage('unstash') {
      agent {
        node {
          label 'master'
        }

      }
      steps {
        unstash 'root'
        sh 'cat root.txt'
      }
    }

  }
}