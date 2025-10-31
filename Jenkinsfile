pipeline {
    agent {
        docker {
            image 'python:3.11'
            args '-u root:root'  // gives permission to write files if needed
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
                sh 'pytest tests/'   // or comment out if no tests
            }
        }

        stage('Print Success') {
            steps {
                echo '✅ Build Successful!'
            }
        }
    }

    post {
        failure {
            echo '❌ Build failed!'
        }
    }
}
