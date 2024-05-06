pipeline {
    agent {
        label 'agent1'
    }

    environment {
        NODE_HOME = '/usr/bin/node'
        PATH = "$NODE_HOME/bin:$PATH"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub repository
                git 'https://github.com/chauhankrishnaa/react-app-demo.git'
            }
        }
        
        
        stage('Install dependencies and build the code') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }
         stage('Build the code') {
            steps { 
                // Build React.js application
                sh 'npm run build'
            }
        }
        
         stage('Start application') {
             steps {
                 // Start React.js application
                 sh 'npm start &'
             }
        }
    }

    post {
        always {
            // Clean up
            sh 'killall node || true'
        }
    }
}
