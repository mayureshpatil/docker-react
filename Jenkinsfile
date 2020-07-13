
pipeline {
    agent any
     stages{
         stage ('docker push'){
             node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', '79f32187-a82b-4e99-bde5-b146a10c4501') {

        def customImage = docker.build("mayureshpatil/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
             }
         }

    stage('Docker Deploy Dev'){
            steps{
                sshagent(['dev-server']) {
                def dockerRun = 'docker run -d --name dockerwebapp -p 40000:8080'
                }
                sh "ssh -o StrictHostKeyChecking=no ubuntu@172.31.4.38 $(dockerRun)"
                }

}
     }
}
