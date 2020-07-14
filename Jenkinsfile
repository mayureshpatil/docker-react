docker.withRegistry('https://registry.hub.docker.com', '79f32187-a82b-4e99-bde5-b146a10c4501') 
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
            
    // some block
}
             sh 'docker push mayureshpatil/dockernode'
         }
        
     }
}
