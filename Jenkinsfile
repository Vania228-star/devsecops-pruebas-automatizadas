Set-Content -Path Jenkinsfile -Value @"
pipeline {
    agent any
    stages {
        stage('Build') {
            steps { echo 'Build: preparando entorno' }
        }
        stage('Test') {
            steps { echo 'Test: pruebas básicas' }
        }
        stage('Analyze') {
            steps { echo 'Analyze: SonarQube (configurar luego)' }
        }
        stage('Security Test') {
            steps { echo 'Security Test: Dependency-Check + ZAP (configurar luego)' }
        }
        stage('Deploy') {
            steps { echo 'Deploy: desplegando app' }
        }
    }
}
"@