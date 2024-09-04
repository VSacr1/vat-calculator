pipeline {
  agent any

  stages {
    
    stage('Checkout') {
       git branch: 'main', url: 'https://github.com/VSacr1/vat-calculator.git'
    }
    
    stage('SonarQube Analysis') {
      def scannerHome = tool 'SonarScanner';
      withSonarQubeEnv() {
        sh "${scannerHome}/bin/sonar-scanner"
      }
    }
  }
}
