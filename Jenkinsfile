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
             docker.withRegistry('https://registry.hub.docker.com', '79f32187-a82b-4e99-bde5-b146a10c4501') {

        def customImage = docker.build("mayureshpatil/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
         }
         }
     }
}
