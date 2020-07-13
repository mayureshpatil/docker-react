
pipeline {
    agent any
     stages{
         stage('docker build'){
             steps{
             sh 'docker build -t mayureshpatiil/dockernode .'
         }
         }
         stage ('docker push'){
             steps{
             withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubp')]) {
                 sh "docker login -u mayureshpatil -p {$dockerHubp}"
    // some block
}
             sh 'docker push mayureshpatil/dockernode'
         }
         }
             
         

   
     }
}

