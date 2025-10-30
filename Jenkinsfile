pipeline {
  agent {
    docker { image 'python:3.12.6' }
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Install') {
      steps {
        sh '''
          pip install -r requirements.txt
        '''
      }
    }

    stage('Test') {
      steps {
        sh 'pytest -q'
      }
    }

    stage('Success') {
      steps {
        echo 'Build Successful!'
      }
    }
  }
}


