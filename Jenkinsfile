podTemplate(label: 'builder',
            containers: [
                containerTemplate(name: 'gradle', image: 'hustakin/jenkins-slave:latest', command: 'cat', ttyEnabled: true),
            ],
            volumes: [
                hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock'),
                hostPathVolume(mountPath: 'home/jenkins/.kube', hostPath: '/root/.kube'),
                
            ]
) {
    node('pod-agent') {
        stage('Build') {
            container('container-agent') {
                sh "kubectl get nodes -o wide"
                sh "ls -al "
            }
        }
        stage('test') {
            container('container-agent') {
                sh "docker ps"
            }
        }
    }
}
