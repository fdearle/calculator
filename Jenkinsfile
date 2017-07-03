pipeline {
  agent any
  stages {
    stage('Build production image') {
      steps {
        sh 'make prod-image'
      }
    }
    stage('Build test image') {
      steps {
        sh 'make test-image'
      }
    }
    stage('Run tests') {
      steps {
        sh 'make test'
      }
    }
    stage('Ask to Continue') {
      steps {
        input 'Should I continue'
      }
    }
  }
}