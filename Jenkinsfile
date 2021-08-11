pipeline{
    agent {node{label 'pod-agent'}} 
    stages{
        stage('Build') {
          steps{
            container('container-agent') {
                sh "kubectl get nodes -o wide"
                sh "ls -al "
            }
          }
        }
        stage('test'){ 
          steps{
            container('container-agent') {
                sh "docker ps"   
            }
          }
        }
    }
}
