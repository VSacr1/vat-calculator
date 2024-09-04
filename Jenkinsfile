pipeline {
  agent any

  stages {
    
    stage('Checkout') {
      steps {
         git branch: 'main', url: 'https://github.com/VSacr1/vat-calculator.git'
      }
    }
    
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'SonarScanner'
      }
      steps {
        withSonarQubeEnv() {
          sh "${scannerHome}/bin/sonar-scanner"
        }
      }
    }
  }
}
