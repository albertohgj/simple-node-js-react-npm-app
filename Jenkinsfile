pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3012:3012'
        }
    }
    environment{
        CI='true'
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('test'){
            steps {
                   sh './jenkins/scripts/test.sh'
            }
        }
    }
}
