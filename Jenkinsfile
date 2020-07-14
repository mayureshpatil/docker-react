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
            
             withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerHUBP')]) {
                 sh "docker login -u mayureshpatil -p {$dockerHUBP}"
    }
             sh 'docker push mayureshpatil/dockernode'
         }
         }
             
         

    stage('Docker Deploy Dev'){
            steps{
               
                sshagent(['dev-server']) {
                 // Remove existing container, if container name does not exists still proceed with the build
                sh script: "ssh ec2-user@172.31.0.38 docker rm -f dockerwebapp ",  returnStatus: true
                sh "ssh -o StrictHostKeyChecking=no ubuntu@172.31.4.38 docker run -p 8080:8080 -d --name dockerwebapp mayureshpatil/dockernode"
                }
                
                }

}
     }
}
