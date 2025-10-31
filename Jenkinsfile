

pipeline {
   
    agent {
        docker {
            image 'python:3.12-slim' 
            args '-u root' // Permissions errors ।
      
        }
    }

    // 2. Stages (Building Blocks of CI/CD)
    stages {
        
        // **Stage 1: Code Checkout (Automatic)**
        stage('Code Checkout') {
            steps {
                
                echo 'GitHub code workspace check out।'
            }
        }

        // **Stage 2: Dependencies Install**
        stage('Install Dependencies') {
            steps {
                echo 'Python dependencies install ...'
                
                dir('app') {
                    sh 'pip install -r requirements.txt'
                    sh 'pip install pytest' // Testing
                }
            }
        }

        // **Stage 3: Build & Run**
        stage('Build & Run App') {
            steps {
                echo 'Python App  build  run...'
            
                dir('app') {
                    sh 'python app.py'
                }
            }
        }

        // **Stage 4: Run Tests**
        stage('Run Tests') {
            steps {
                echo 'Basic tests run कर रहे हैं...'
           
                dir('app') {
                    sh 'pytest test_app.py' 
                }
            }
        }

        // **Stage 5: Finalize**
        stage('Finalize') {
            steps {
                echo 'Build Successful! ✅' // Success message 
            }
        }
    }
    
    // **Post-Build Actions**
    post {
        always {
          
            cleanWs()
        }
    }
}
