pipeline {
    agent any
    tools {
        maven 'maven'
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn compile'
            }
        }
        
        stage('Sonarqube analysis') {
            environment {
                SONAR_HOST_URL = 'http://192.168.56.1:9000/'
                SONAR_AUTH_TOKEN = credentials('sonarqube')
            }
            steps {
                sh 'mvn sonar:sonar -Dsonar.projectKey=sample_project -Dsonar.host.url=$SONAR_HOST_URL -Dsonar.login=$SONAR_AUTH_TOKEN'
            }
        }
    }
}
