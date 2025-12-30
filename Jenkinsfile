pipeline {
    agent any

    environment {
        IMAGE_NAME = "jenkins-nginx-demo"
        CONTAINER_NAME = "jenkins-nginx-container"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %IMAGE_NAME% .'
            }
        }

        stage('Remove Old Container') {
            steps {
                bat '''
                docker stop %CONTAINER_NAME% || exit 0
                docker rm %CONTAINER_NAME% || exit 0
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                bat '''
                docker run -d -p 8081:80 --name %CONTAINER_NAME% %IMAGE_NAME%
                '''
            }
        }
    }

    post {
        success {
            echo "CI/CD completed successfully 🚀"
        }
    }
}
