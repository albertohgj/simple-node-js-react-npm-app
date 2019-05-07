pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3012:3000'
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
        stage('Deliver'){
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Quieres finalizar? (Click "Proceed" to Continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
