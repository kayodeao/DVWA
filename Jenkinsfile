pipeline {
    agent any
    
    stages {
        stage('SCM') {
            steps {
                // Checkout source code from SCM
                checkout scm
            }
        }
        stage('SonarQube Analysis') {
            steps {
                // Define SonarScanner tool
                def scannerHome = tool 'SonarScanner';
                // Run SonarScanner analysis
                withSonarQubeEnv() {
                    sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=DVWA-Scan2"
                }
            }
        }
    }
}
