pipeline {
  agent any
  stages {
    stage('Build production image') {
      steps {
        sh 'docker build -t calculator -f Dockerfile.production .'
      }
    }
    stage('Build test image') {
      steps {
        sh 'docker build -t calculator-test -f Dockerfile.test .'
      }
    }
    stage('Run tests') {
      steps {
        sh 'docker run --rm calculator-test'
      }
    }
    stage('Ask to Continue') {
      steps {
        input 'Should I continue'
      }
    }
  }
}