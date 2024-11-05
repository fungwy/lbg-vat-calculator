pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/fungwy/lbg-vat-calculator.git'
      }

    }
    stage('SnarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
          withSonarQubeEnv('sonar-qube-1') {
            sh "${scannerHome}/bin/sonar-scanner"
          }
        }
    }
  }
}
