pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                eksctl get clusters --region us-east-1
                kubectl get pods
                
               
                '''
      }
    }
  }
}


