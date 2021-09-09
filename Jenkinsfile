pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building Pipelines'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing Pipeline echo'
            echo "Driver Path:-  ${ChromeDriverPath}"
          }
        }

        stage('Logging') {
          environment {
            LocalVariable = 'HelloLocal'
          }
          steps {
            echo 'Logging to File'
            writeFile(file: 'LogsFile.txt', text: "Logging everything ${ChromeDriverPath} with local variable value ${LocalVariable}")
          }
        }

      }
    }

    stage('Deploy') {
      when {
        branch 'master'
      }
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Ready to Deploy', id: 'OK')
            echo 'Deploying to Server'
            retry(count: 3) {
              echo 'retry'
            }

          }
        }

        stage('Archive Artifacts') {
          steps {
            archiveArtifacts 'LogsFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:/Chromedriver.exe'
  }
}