{
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
