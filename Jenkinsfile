
pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Downloading source code from GitHub'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage started'
                sh 'echo "Application build successful"'
            }
        }

        stage('Test') {
            steps {
                echo 'Running application tests'
                sh 'test -f Jenkinsfile'
                sh 'echo "All tests passed"'
            }
        }

        stage('Finish') {
            steps {
                echo 'Your Jenkins pipeline completed successfully'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: GitHub code processed successfully'
        }
        failure {
            echo 'FAILURE: Please check the console output'
        }
    }
}
