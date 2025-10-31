pipeline {
    agent any

    stages {
        stage('Clone from GitHub') {
            steps {
                git 'https://github.com/codewithahsaan/Dockers-Jenkins-Pipeline.git'
            }
        }

        stage('Build Python App') {
            steps {
                echo 'Building the Python app...'
                bat 'docker build -t python-app .'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                bat 'docker run --rm python-app python -m unittest test_app.py'
            }
        }

        stage('Print Success') {
            steps {
                echo 'Build Successful!'
            }
        }
    }

    post {
        failure {
            echo 'Build failed!'
        }
    }
}
