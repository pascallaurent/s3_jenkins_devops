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
    stage("Upload to S3") {
      steps {
        withAWS(region:'us-east-1',credentials:'s3_jenkins_devops') {
          s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'skdevops.sokibi.com')
        }
      }
    }
  }
}
