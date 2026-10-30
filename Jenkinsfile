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

        stage('Preparar dependencia vulnerable') {
    steps {
        sh 'mkdir -p libs && curl -sSL -o libs/log4j-core-2.14.1.jar https://repo1.maven.org/maven2/org/apache/logging/log4j/log4j-core/2.14.1/log4j-core-2.14.1.jar'
    }
}
        stage('Security Test') {
            steps {
                dependencyCheck additionalArguments: '--scan . --format HTML --format XML --enableExperimental', odcInstallation: 'dependency-check', nvdCredentialsId: 'nvd-api-key'
                dependencyCheckPublisher pattern: 'dependency-check-report.xml'
            }
      }
        stage('Deploy') {
            steps { echo 'Deploy: desplegando app' }
        }
    }
}