pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                eksctl get clusters --region us-east-1
                kubectl get all
                kubectl run my-first-pod --image stacksimplify/kubenginx:1.0.0 --generator=run-pod/v1
                kubectl apply -f 01-front-end-App-Deployment-and-NodePortService.yml
                
               
                '''
      }
    }
  }
}


