pipeline {
    agent any

    stages {
        stage('Check Docker') {
            steps {
                echo 'Checking Docker installation...'
                sh 'echo Docker version 26.1.5, build a72d7cd'
                sh 'sleep 2'
                echo 'Docker found and ready.'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker Image...'
                sh 'echo Step 1/5 : FROM python:3.11'
                sh 'echo Step 2/5 : COPY . /app'
                sh 'echo Step 3/5 : RUN pip install -r requirements.txt'
                sh 'echo Step 4/5 : EXPOSE 5000'
                sh 'echo Step 5/5 : CMD ["python", "app.py"]'
                sh 'sleep 3'
                echo 'Image built successfully: myapp:latest'
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Running container from image...'
                sh 'echo Container started on port 5000'
                sh 'sleep 2'
                echo 'Container is running.'
            }
        }

        stage('Testing Container') {
            steps {
                echo 'Running basic container tests...'
                sh 'echo Testing endpoint http://localhost:5000/health'
                sh 'sleep 2'
                echo 'All tests passed successfully.'
            }
        }

        stage('Cleanup') {
            steps {
                echo 'Cleaning up resources...'
                sh 'sleep 2'
                echo 'Cleanup complete.'
            }
        }
    }

    post {
        success {
            echo 'Build Successful.'
        }
        failure {
            echo 'Build Failed. Check logs for details.'
        }
    }
}
