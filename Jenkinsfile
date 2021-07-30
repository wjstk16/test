podTemplate(label: 'builder',
            containers: [
                containerTemplate(name: 'gradle', image: 'hustakin/jenkins-slave:latest', command: 'cat', ttyEnabled: true),
            ]) {
    node('builder') {
        stage('Build') {
            container('gradle') {
                sh "kubectl"
            }
        }
        stage('test') {
            container('gradle') {
                sh "docker ps"
            }
        }
    }
    
}
