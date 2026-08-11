pipeline {
    agent any

    stages { 
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                
                
             }
        }  
        stage('Build') {
            steps {
                sh 'python3 --version'
                sh 'python3 -m venv venv'
                sh 'venv/bin/pip install --upgrade pip'
                sh 'venv/bin/pip install -r requirements.txt'
             }
        }
        stage('Test') {
            steps {
                echo 'Testing Flask application...'
            }
        }
        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
            }
        }
    }
}