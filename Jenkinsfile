
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
                 sh "docker login -u mayureshpatil -p Mayu@1234"
  
             sh 'docker push mayureshpatil/dockernode:2.0.0'
         }
         }
             
         

   
     }
}

