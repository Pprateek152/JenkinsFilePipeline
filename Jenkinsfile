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
            echo "Driver Path:- ${ChromeDriverPath}"
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
  environment {
    ChromeDriverPath = 'C:/Chromedriver.exe'
  }
}
