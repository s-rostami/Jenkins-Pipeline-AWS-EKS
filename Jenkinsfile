pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                eksctl get clusters --region us-east-1
                strace kubectl version
                kubectl run frontend --image public.ecr.aws/o8f5t9n7/frontend-v1
               
                '''
      }
    }
  }
}


