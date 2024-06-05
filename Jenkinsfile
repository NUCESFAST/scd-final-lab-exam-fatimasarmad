pipeline {
    agent any
    
    stages {
        stage('21i-1139 Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/fatimasarmad/lab10-11'
            }
        }
        
        stage('21i-1139 Dependency Installation') {
            steps {
                bat 'npm install' // Assuming npm is used for dependency installation
            }
        }
        
        stage('21i-1139 Build Docker Image') {
            steps {
                bat 'docker build -t your_image_name .'
            }
        }
        
        stage('21i-1139 Run Docker Image') {
            steps {
                bat 'docker run -d -p 3000:3000 your_image_name'
            }
        }
        
    }
}