pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building Pipeline'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing Pipeline'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying to Server'
      }
    }

  }
}