podTemplate(label: 'builder',
            containers: [
                containerTemplate(name: 'gradle', image: 'hustakin/jenkins-slave:latest', command: 'cat', ttyEnabled: true),
            ],
            volumes: [
                hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock'),
                hostPathVolume(mountPath: 'home/jenkins/.kube', hostPath: '/root/.kube'),
                
            ]
)
pipeline{
    agent {node{label 'builder'}} 
    stages{
        stage('Build') {
          steps{
            container('gradle') {
                sh "kubectl get nodes -o wide"
                sh "ls -al "
            }
          }
        }
        stage('test'){ 
          steps{
            container('gradle') {
                sh "docker ps"
            }
          }
        }
    }
}

