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
                sh 'venv/bin/pytest'
             }
        } 
        stage('Docker Build') {
            steps {
                sh 'docker build -t devops-learning-dashboard .'
            }
        }
        stage('Docker Run') {
            steps {
                sh 'docker stop devops-learning-dashboard || true'
                sh 'docker rm devops-learning-dashboard || true'
                sh 'docker run -d --name devops-learning-dashboard -p 5001:5001 devops-learning-dashboard:latest'
            }
        }
        stage('Health Check') {
            steps {
                sh 'sleep 5'
                sh 'curl -f http://localhost:5001'
            }
        }
    }
}