pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = credentials('dckr_pat_FRDScylyoOGzQYggJgWlFlThNZM')
        DOCKER_HUB_REPO = 'fatimasarmadd/21i1139finalexamscd_p'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/NUCESFAST/scd-final-lab-exam-fatimasarmad.git'
            }
        }

        stage('Dependency Installation') {
            steps {
                bat 'npm install' // Assuming npm is used for dependency installation
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("${DOCKER_HUB_REPO}:${env.BUILD_ID}")
                }
            }
        }

        stage('Run Docker Image') {
            steps {
                bat 'docker run -d -p 3000:3000 ${DOCKER_HUB_REPO}:${env.BUILD_ID}'
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_HUB_CREDENTIALS) {
                        dockerImage.push()
                        dockerImage.push('latest')
                    }
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
