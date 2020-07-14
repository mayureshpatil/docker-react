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
             withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerHUBP')]) {{
                 sh "docker login -u mayureshpatil -p {$dockerHUBP}"
    // some block
}
             sh 'docker push mayureshpatil/dockernode'
         }
         }
