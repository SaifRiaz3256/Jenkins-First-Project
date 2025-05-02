pipeline {
  agent none

  stages {
    stage('Build Backend') {
      agent {
        docker {
          image 'maven:3.8.1-openjdk-11'
        }
      }
      steps {
        echo 'Building the backend...'
        sh 'mvn -v'
      }
    }

    stage('Build Frontend') {
      agent {
        docker {
          image 'node:16-alpine'
        }
      }
      steps {
        echo 'Building the frontend...'
        sh 'node -v'
      }
    }

    stage('Success Message') {
      agent any
      steps {
        echo '✅ Pipeline completed successfully!'
      }
    }
  }
}
