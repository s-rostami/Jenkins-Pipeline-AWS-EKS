pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                ~/kubectl apply -f 01-front-end-App-Deployment-and-NodePortService.yml
                '''
      }
    }
  }
}


