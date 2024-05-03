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
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']], name
                    userRemoteConfigs: [[url: 'https:// https://github.com/MaheswaranPalaniselvan/devops_assignment_1.git ']]])
                    }
            }
        }
        stage('Build and Compile') {
            steps {
                sh 'make clean && make all'
                
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
                    }
                failure {
                    echo 'Build failed! Please check the build logs.'
                    }
                }
        }
    }
}
