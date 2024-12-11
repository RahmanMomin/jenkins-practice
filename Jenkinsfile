pipeline {
  agent none
  stages {
    stage('Back-end') {
      agent {
        docker { image 'openjdk:17' }
      }
      steps {
        sh '''
          cd backend
          javac App.java 
          javac App.java
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
          node app.js 
        '''
      }
    }
  }
}
