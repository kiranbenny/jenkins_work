pipeline {
    agent any // Runs on any available executor

    stages {
        stage('Checkout') {
            steps {
                // Pulls code from your git repo
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Use 'sh' for Linux/Mac or 'bat' for Windows
                bat './mvnw clean package' 
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                bat './mvnw test'
            }
        }
    }
    
    post {
        always {
            echo 'I will always run, regardless of success or failure!'
        }
    }
}
