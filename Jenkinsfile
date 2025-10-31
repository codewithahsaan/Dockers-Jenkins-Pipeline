pipeline {
    agent {
        docker {
            image 'python:3.11'
            args '-u root:root' // optional, for permissions
        }
    }

    stages {
        stage('Build Python App') {
            steps {
                sh 'python3 app.py'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest tests/'
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
