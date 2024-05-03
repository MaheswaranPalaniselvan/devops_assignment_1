pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build and Compile') {
            steps {
                sh 'make clean'
                sh 'make'
            }
        }
    }
}
