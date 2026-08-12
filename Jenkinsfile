pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS' // Matches the name you gave in Jenkins Tools
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
            }
        }
        stage('Build') {
            steps {
                bat 'npm install'
                bat 'npm run build'
            }
        }
        stage('Test') {
            steps {
                bat 'set CI=true && npm test'
            }
        }
    }
}
