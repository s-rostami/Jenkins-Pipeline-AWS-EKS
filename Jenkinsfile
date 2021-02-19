pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                strace kubectl version
                kubectl get po
               
                '''
      }
    }
  }
}


