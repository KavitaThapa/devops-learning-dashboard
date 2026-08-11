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
                echo 'Building Flask application...'
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