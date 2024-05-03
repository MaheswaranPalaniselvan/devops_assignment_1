pipeline {
    agent any

    triggers {
        scm { 
            branches '**'
        }
    }

    stages {
        stage('Checkout Code') {
            steps {
                script {
                    git branch: 'master', 
                       credentialsId: '8b8a4dfa-903d-4d7f-8969-f27da7513442', 
                       url: 'https://github.com/MaheswaranPalaniselvan/devops_assignment_1.git' 
                }
            }
        }
        stage('Build and Compile') {
            steps {
                script {
                    sh 'make clean && make all'
                }
            }
        }
    }
}
