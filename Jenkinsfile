pipeline {
  agent any
  stages {
    stage('ttt') {
      steps {
        sh 'ssh host -t "argocd app sync test"'
      }
    }

  }
}