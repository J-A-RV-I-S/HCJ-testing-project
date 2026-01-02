pipeline {
  agent any
  
  environment {
    IMAGE_NAME= "HCJ-testing-project"
    IMAGE_TAG= "1.0"
  }

  stages {
    stage('Checkout Code') {
      steps {
        echo 'Cloning github repository'
        checkout scm
      }
    }

    stage('Build HCJ Application') {
      steps {
        sh '''
        echo 'Good Going...'
        '''
      }
    }

    stage('Build Docker Image') {
      steps {
        echo 'Building docker image'

        sh '''
          docker --version
          docker build -t $IMAGE_NAME:$IMAGE_TAG .
        '''
      }
    }
  }
  post {
    success {
      echo 'Pipeline completed successfully'
    }
    failure {
      echo 'Pipeline failed'
    }
  }
}
