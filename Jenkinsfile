pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Koushick25/agilelab2.2.git'
            }
        }
        stage('Parallel Checks') {
            parallel {
                stage('Frontend Check') {
                    steps {
                        bat 'python frontend_check.py'
                    }
                }
                stage('Backend Check') {
                    steps {
                        bat 'python backend_check.py'
                    }
                }
            }
        }
        stage('Summary') {
            steps {
                echo 'both the frontend and backend checks are completed '
            }
        }
    }
}