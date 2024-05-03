pipeline {
  agent any


  stages {
    stage('Checkout Code') {
      steps {
        checkout(
          [$class: 'GitSCM',
            branches: [[name: '*/main']],
            credentialsId: '8b8a4dfa-903d-4d7f-8969-f27da7513442', // Replace with your credential ID
            url: 'https://github.com/MaheswaranPalaniselvan/devops_assignment_1.git'
          ]
        )
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
