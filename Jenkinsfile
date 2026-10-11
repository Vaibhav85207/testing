
pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'Source code checked out successfully'
            }
        }

        stage('Validate Git') {
            steps {
                bat 'git --version'
                bat 'git status --short'
                bat 'git log -1 --oneline'
            }
        }

        stage('Test') {
            steps {
                echo 'Starter test passed'
            }
        }
    }

    post {
        success {
            echo 'CI pipeline completed successfully!'
        }
        failure {
            echo 'CI pipeline failed. Check the console output.'
        }
    }
}