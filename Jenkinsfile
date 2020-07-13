
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
             withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
                 sh "docker login -u mayureshpatil -p {$dockerHubPwd}"
    // some block
}
             sh 'docker push mayureshpatil/dockernode:2.0.0'
         }
         }
             
         

   
     }
}

