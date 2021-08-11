podTemplate(label: 'builder',
            containers: [
                containerTemplate(name: 'gradle', image: 'hustakin/jenkins-slave:latest', command: 'cat', ttyEnabled: true),
            ],
            volumes: [
                hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock'),
                hostPathVolume(mountPath: 'home/jenkins/.kube', hostPath: '/root/.kube'),
                
            ]
) {
    node('builder') {
        stage('Build') {
            container('gradle') {
                sh "kubectl get nodes -o wide"
                sh "ls -al "
            }
        }
        stage('test') {
            container('gradle') {
                sh "docker ps"
            }
        }
    }
}
