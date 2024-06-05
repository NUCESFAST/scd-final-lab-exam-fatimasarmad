pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/fatimasarmad/lab10-11'
            }
        }
        
        stage('Dependency Installation') {
            steps {
                bat 'npm install' // Assuming npm is used for dependency installation
            }
        }
        
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t your_image_name .'
            }
        }
        
        stage('Run Docker Image') {
            steps {
                bat 'docker run -d -p 3000:3000 your_image_name'
            }
        }
        
    }
}