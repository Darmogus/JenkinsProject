pipeline {
    agent none
    stages {
        stage("Build and analysis with SonarQube") {
            agent any
            steps {
                script {
                    sh 'mvn clean package sonar:sonar'
                }
            }
        }
    }
}
