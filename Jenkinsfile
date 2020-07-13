
pipeline {
    agent any
     stages{
         stage ('docker push'){
             steps{
    docker.withRegistry('https://registry.hub.docker.com', '79f32187-a82b-4e99-bde5-b146a10c4501') {

        def customImage = docker.build("mayureshpatil/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
             }
         }
         

    stage('Docker Deploy Dev'){
            steps{
                def dockerRun = 'docker run -p 8080:8080 -d --name dockerwebapp 8080'
                sshagent(['dev-server']) {
                sh "ssh -o StrictHostKeyChecking=no ubuntu@172.31.4.38 ${dockerRun}"
                }
                
                }

}
     }
}

