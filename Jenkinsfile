
pipeline {
    agent any
     stages{
         stage('docker build'){
             sh 'docker build -t mayureshpatiil/dockernode .'
         }
         stage ('docker push'){
             withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubp')]) {
                 sh "docker login -u mayureshpatil -p {$dockerHubp}"
    // some block
}
             sh 'docker push mayureshpatil/dockernode'
            
             
         

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

