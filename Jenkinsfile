pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                build 'PES1UG21CS338-1'
                sh 'g++ sample.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            step {
                echo 'deploy'
            }
        }
    }
    post{
        failure{
            error 'Pipeline failed'
        }
    }
}
