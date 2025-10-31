pipeline {
    agent any

    stages {
        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run --rm myapp:latest'
            }
        }
    }

    post {
        success {
            echo '✅ Docker build and run successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
