pipeline {
  agent any
  stages {
    stage('Build') {
      steps{
                sh '''
                eksctl create nodegroup --cluster=eks1 \
                       --region=us-east-1 \
                       --name=node-server-ng-public1 \
                       --node-type=t3.medium \
                       --nodes=2 \
                       --nodes-min=2 \
                       --nodes-max=4 \
                       --node-volume-size=20 \
                       --ssh-access \
                       --ssh-public-key=kube-demo \
                       --managed \
                       --asg-access \
                       --external-dns-access \
                       --full-ecr-access \
                       --appmesh-access \
                       --alb-ingress-access 
                       
                kubectl apply -f 01-front-end-App-Deployment-and-NodePortService.yml
                '''
      }
    }
  }
}


