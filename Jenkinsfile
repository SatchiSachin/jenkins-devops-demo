pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'git@github.com:SatchiSachin/jenkins-devops-demo.git'
            }
        }

        stage('Build Step') {
            steps {
                echo 'Build completed successfully'
            }
        }
    }
}
