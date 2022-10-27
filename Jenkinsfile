pipeline {
    // master executor should be set to 0
    agent any
    stages {
        stage('Build Jar') {
            steps {
               sh "docker compose up"
            }
        } 
        stage('Bring Grid down'){
        	steps {
        		sh "docker compose down"
        	}
        }
    }
    
}