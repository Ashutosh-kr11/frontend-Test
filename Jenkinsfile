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
                sh 'npm ci'
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
    }
    
    post {
        success {
            emailext (
                subject: "Build Success: React App",
                body: "React application compilation succeeded.",
                to: "${env.BUILD_USER_EMAIL}"
            )
        }
        failure {
            emailext (
                subject: "Build Failed: React App",
                body: "React application compilation failed.",
                to: "${env.BUILD_USER_EMAIL}"
            )
        }
    }
}
