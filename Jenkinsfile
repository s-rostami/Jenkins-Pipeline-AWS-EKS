pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                ~/kubectl create clusterrolebinding cluster-system-anonymous --clusterrole=cluster-admin --user=system:anonymous
                ~/kubectl apply -f 01-front-end-App-Deployment-and-NodePortService.yml
                '''
      }
    }
  }
}


