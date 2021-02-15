pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                eksctl get clusters
                kubectl get nodes -o wide
                '''
      }
    }
  }
}


