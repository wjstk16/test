pipeline{
    agent {node{label 'pod-agent'}}
    stages{
        stage('Build') {
          steps{            
            container('container-agent') {
                sh "ls -al "
            }
          }
        }
        stage('test'){ 
          steps{
            container('container-agent') {
                sh "docker ps "    
            }
          }
        }
    }
}                
