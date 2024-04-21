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
                // Define SonarScanner tool and specify its installation name
                def scannerHome = tool name: 'SonarScanner';
                // Run SonarScanner analysis
                withSonarQubeEnv('SonarScanner') {
                    sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=DVWA-Scan2"
                }
            }
        }
    }
}
