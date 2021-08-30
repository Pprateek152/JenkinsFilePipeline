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
            echo 'Testing Pipeline echo'
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
