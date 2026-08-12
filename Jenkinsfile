pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Installing dependencies and building React app...'
                // Use 'bat' for Windows, or 'sh' for Linux/Mac
                bat 'npm install'
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running React Unit Tests...'
                // CI=true prevents Jest from running in interactive watch mode
                bat 'set CI=true && npm test'
            }
        }
    }
}
