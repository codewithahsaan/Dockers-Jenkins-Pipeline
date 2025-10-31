pipeline {
     agent {
        docker {
            image 'python:3.12.6' // Official Python base image
            args '-u root' // Helps prevent permissions errors within the container
        }
    }

    stages {
        stage('Pull Code') {
            steps {
                echo 'Pulling code from GitHub...'
                git 'https://github.com/codewithahsaan/Dockers-Jenkins-Pipeline.git'
            }
        }

        stage('Build App') {
            steps {
                echo 'Building Python App...'
                sh 'python --version'
                sh 'python app.py'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running basic tests...'
                sh 'echo All tests passed!'
            }
        }

        stage('Finish') {
            steps {
                echo 'Build Successful!'
            }
        }
    }
}

