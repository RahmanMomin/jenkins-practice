pipeline {
  agent none
  stages {
    stage('Back-end') {
      agent {
        docker { image 'maven:3.8.1-adoptopenjdk-11' }
      }
      steps {
        sh '''
          cd backend
          mvn clean compile exec:java -Dexec.mainClass="App" 
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
