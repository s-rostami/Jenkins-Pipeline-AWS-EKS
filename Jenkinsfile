pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                kubectl get nodes -o wide
                '''
      }
    }
  }
}


