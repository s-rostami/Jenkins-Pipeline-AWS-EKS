pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                eksctl get clusters --region us-east-1
                kubectl apply -f 01-front-end-App-Deployment-and-NodePortService.yml
                
               
                '''
      }
    }
  }
}


