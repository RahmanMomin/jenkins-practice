pipeline {
  agent none
  stages {
    stage('Checkout Code') {
      agent any
      steps {
        git branch: 'main', url: 'https://github.com/RahmanMomin/jenkins-practice.git' 
      }
    }
    stage('Back-end') {
      agent {
        docker { image 'openjdk:17' }
      }
      steps {
        sh '''
           cd backend
          javac App.java 
          java App 
        '''
      }
    }
    stage('Front-end') {
      agent {
        docker { image 'node:16-alpine' }
      }
      steps {
        sh '''
          cd frontend
          node index.js
        '''
      }
    }
  }
}
