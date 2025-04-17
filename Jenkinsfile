pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    environment {
        PORT = '3001'
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/guptajii30/Practical-4.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Application') {
            steps {
                bat 'npm start'
            }
        }
    }

    post {
        success {
            echo "✅ Application started successfully on port ${env.PORT}!"
        }
        failure {
            echo "❌ Build failed—check the logs above."
        }
    }
}
