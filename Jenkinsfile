pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/SatchiSachin/jenkins-devops-demo.git'
            }
        }

        stage('Build Step') {
            steps {
                echo 'Build completed successfully'
            }
        }
    }
}
