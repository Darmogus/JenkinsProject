pipeline {
    agent any
    stages {
        stage('Build and Analysis with SonarQube') {
            steps {
                script {
                    sh 'mvn clean package sonar:sonar'
                }
            }
        }
    }
}
