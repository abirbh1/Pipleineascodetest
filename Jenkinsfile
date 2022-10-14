pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'build is completed'
        timeout(time: 5, unit: 'SECONDS') {
    // some block
           sh 'sleep 5'}
      }
    }
    stage('Test') {
      steps {
        echo 'test is completed'
      }
    }

  }
}