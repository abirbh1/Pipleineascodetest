pipeline {
  agent any
  stages {
    stage('Build jar') {
      steps {
        script {
          echo"building the application...4"
          sh 'mvn package'
        }

      }
    }

    stage('Build image') {
      steps {
        script {
          echo"building the image"
          withCredentials([usernamePassword(credentialsId: 'docker_hub_repo', passwordVariables: 'PASS' , usernameVariable: 'USER')])
          sh 'docker build -t abibh1/demo-app:jma-1.0 .'
          sh "echo $PASS | docker login -u $USER --password-stdin"
          sh ' docker push abibh1/demo-app:jma-1.0'
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying the application'
      }
    }

  }
  tools {
    maven Maven
  }
}