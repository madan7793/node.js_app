pipeline {
   agent any
  
   environment {
       DOCKER_HUB_REPO = "madanmohan7793/node_app"
       CONTAINER_NAME = "node-hello-world"
       DOCKERHUB_CREDENTIALS=credentials('dockerhub_credential')
   }
  
   stages {
       
      
       stage('Build') {
           steps {
               echo 'Building..'
               sh 'docker image build -t $DOCKER_HUB_REPO:latest .'
           }
       }
       stage('Push') {
           steps {
               echo 'Pushing image..'
               sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
               sh 'docker push $DOCKER_HUB_REPO:latest'
           }
       }
   }
}
