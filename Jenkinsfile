node('jenkins-jnlp') {
    env.MVN_HOME = "${tool 'Maven'}"
    env.PATH="${env.MVN_HOME}/bin:${env.PATH}"

    stage('Prepare') {
        echo "1.Prepare Stage"
        checkout scm
        sh "docker ps"
        sh "kubectl get po"
    }
    
}
