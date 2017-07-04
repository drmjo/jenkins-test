pipeline {
  agent none
  stages {
    stage('Node Version') {
      agent {
        docker 'node'
      }
      steps {
        sh 'node --version && env'
      }
    }
    stage('2 PHP versions') {
      agent {
        docker 'php'
      }
      steps {
        parallel v1: {
          sh 'php --version && env'
        }, v2: {
          sh 'php --version'
        }
      }
    }
    stage('Go Version') {
      agent {
        docker 'golang'
      }
      steps {
        sh 'go version'
        sh 'go version && env'
        sh 'go version'
      }
    }
  }
}
