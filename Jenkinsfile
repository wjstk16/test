podTemplate(label: 'builder',
            containers: [
                containerTemplate(name: 'gradle', image: 'gradle:5.6-jdk8', command: 'cat', ttyEnabled: true),
            ],
            volumes: [
                hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock'),
                hostPathVolume(mountPath: 'home/jenkins/.kube', hostPath: '/root/.kube'),
                #hostPathVolume(mountPath: '/usr/local/bin/argocd', hostPath: '/usr/local/bin/argocd'),
            ]
) {
    node('builder') {
        stage('Build') {
            container('gradle') {
                sh "kubectl get nodes -o wide"
            }
        }
        stage('test') {
            container('gradle') {
                sh "docker ps"
            }
        }
    }
    
}
