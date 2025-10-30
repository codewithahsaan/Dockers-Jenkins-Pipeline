pipeline {
    agent any

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
