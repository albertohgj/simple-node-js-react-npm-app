pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3011:3011' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
