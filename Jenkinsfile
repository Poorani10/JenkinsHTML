
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Poorani10/JenkinsHTML.git'
            }
        }

        stage('Testing') {
            steps {
                bat 'if not exist index.html exit /b 1'
                bat 'findstr /C:"<html>" index.html'
                echo 'HTML tests passed'
            }
        }

        stage('Deployment') {
            steps {
                bat 'if not exist deployed mkdir deployed'
                bat 'copy /Y index.html deployed\\index.html'
                echo 'Deployment completed'
            }
        }
    }
}
