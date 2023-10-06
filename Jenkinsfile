pipeline {
    agent {
      docker {
          image 'node:20'
        }
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