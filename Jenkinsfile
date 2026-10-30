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
            steps {
                dependencyCheck additionalArguments: '--scan . --format HTML --format XML --enableExperimental', odcInstallation: 'dependency-check'
                dependencyCheckPublisher pattern: 'dependency-check-report.xml'
            }
        }
        stage('Deploy') {
            steps { echo 'Deploy: desplegando app' }
        }
    }
}