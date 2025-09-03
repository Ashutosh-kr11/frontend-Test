pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS'
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Using npm install instead of npm ci since package-lock.json may not exist
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                // Set CI=false to prevent treating warnings as errors
                sh 'CI=false npm run build'
            }
        }
    }
    
    post {
        success {
            emailext (
                subject: "Build Success: React App",
                body: "React application compilation succeeded.",
                to: "ashutosh.devpro@gmail.com" // Replace with actual email address
            )
        }
        failure {
            emailext (
                subject: "Build Failed: React App",
                body: "React application compilation failed.",
                to: "ashutosh.devpro@gmail.com" // Replace with actual email address
            )
        }
    }
}
