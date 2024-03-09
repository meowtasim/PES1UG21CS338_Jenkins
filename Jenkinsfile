pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install'  // Assuming mvn is a typo for your actual build command
      }
      echo 'Build stage successful'
    }
    stage('Test') {
      steps {
        sh 'mvn test'  // Assuming mvn is a typo for your actual test command
      }
      echo 'Test stage successful'
      post {
        always {
          junit 'target/surefire-reports/*.xml'
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'mvn deploy'  // Assuming mvn is a typo for your actual deployment command
      }
      echo 'Deployment Successful'
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
