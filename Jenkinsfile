pipeline {
    agent any
    
    environment {
        // Set the PATH to include the location where npm is installed.
        PATH = "${tool 'Node.js'}/bin:${env.PATH}"
    }
    
    stages {
      stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
              sh 'npm install'
            }
        }
        stage('Build') {
            steps {
              sh "npm run test"
            }
        }
        stage('Test') {
            steps {
              sh "npm run test"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        post {
          success {
              echo 'The build was successful!'
          }
          failure {
              echo 'The build failed :('
          }
      }
    }
}