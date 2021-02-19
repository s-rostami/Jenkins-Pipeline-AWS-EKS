pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                kubectl run front-end --image public.ecr.aws/o8f5t9n7/frontend-v1 --generator=run-pod/v1
                kubectl apply -f 01-front-end-App-Deployment-and-NodePortService.yml
                '''
      }
    }
  }
}


