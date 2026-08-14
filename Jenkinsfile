pipeline {
    agent any

    tools {
        nodejs 'NodeJS' // Matches the name in Jenkins Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub...'
                // Jenkins automatically handles git checkout when configured via SCM
            }
        }

        stage('Build') {
            steps {
                echo 'Installing dependencies and building React application...'
                bat 'npm ci'
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Executing React unit tests...'
                // Setting CI=true prevents Jest from hanging in watch mode
                bat 'set CI=true&& npm test -- --passWithNoTests'
            }
        }

        stage('Validation') {
            steps {
        echo 'Performing code and environment validation...'
        bat 'IF EXIST package.json (echo Package manifest verified successfully.) ELSE (echo Missing package.json && exit 1)'
    }
        }
    }

    post {
        always {
            echo 'Pipeline execution complete.'
        }
    }
}
