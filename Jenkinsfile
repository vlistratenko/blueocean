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
        sh './create_file.sh'
      }
    }

  }
}