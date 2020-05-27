pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build step'
          }
        }

        stage('Buil2') {
          steps {
            echo 'parallel2'
          }
        }

        stage('Build3') {
          steps {
            retry(count: 2) {
              sh 'echo "today is $date"'
            }

          }
        }

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
        archiveArtifacts(artifacts: 'artifact.jar', fingerprint: true, onlyIfSuccessful: true, excludes: '*.log')
      }
    }

  }
}