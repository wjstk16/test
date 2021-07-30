pipeline {
  agent any
  stages {
    stage('Triggering') {
      steps {
        sh 'ls'
      }
    }

    stage('TB Deploy') {
      parallel {
        stage('TB 1 Deploy') {
          steps {
            sh 'ssh host -t "argocd app sync test"'
          }
        }

        stage('TB 2 Deploy') {
          steps {
            sh 'ls'
          }
        }

      }
    }

    stage('TB Testing') {
      parallel {
        stage('CNF Test') {
          steps {
            sh 'ls'
          }
        }

        stage('E2E Test') {
          steps {
            sh 'ls'
          }
        }

      }
    }

    stage('Production Deploy') {
      steps {
        sh 'ssh host -t "argocd app sync test"'
      }
    }

    stage('Prod Testing') {
      parallel {
        stage('CNF Test') {
          steps {
            sh 'ls'
          }
        }

        stage('E2E Test') {
          steps {
            sh 'ls'
          }
        }

      }
    }

    stage('Mornitoring') {
      steps {
        sh 'ls '
      }
    }

  }
}
