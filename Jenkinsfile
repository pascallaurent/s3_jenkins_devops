pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo \'Hello DevOps\''
      }
    }
    stage("Lint HTML") {
      steps {
        sh "tidy -q -e *.html"
      }
    }
  }
}
