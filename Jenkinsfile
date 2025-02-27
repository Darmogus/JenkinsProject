pipeline {
    agent any
    tools {
        maven 'maven'
    }
    
    stages {
        stage('Building Application') {
            steps {
                echo 'Building Application'
                sh 'mvn compile'
            }
        }
        
        stage('Sonarqube analysis') {
            environment {
                SONAR_HOST_URL = 'http://192.168.56.1:9000/'
                SONAR_AUTH_TOKEN = credentials('sonarqube')
            }
            steps {
                // Commande Maven pour SonarQube sans spécifier de sous-dossiers
                echo 'Sonarqube analysis'
                sh '''
                mvn sonar:sonar \
                    -Dsonar.projectKey=sample_project \
                    -Dsonar.host.url=$SONAR_HOST_URL \
                    -Dsonar.login=$SONAR_AUTH_TOKEN
                '''
            }
        }

        stage('Deploy & OWASP Dependency-Check') {
            agent any
            steps {
                dependencyCheck additionalArguments '''
                    -o './'
                    -s './'
                    -f 'ALL'
                    --prettyPrint''', odcInstallation: 'owasp-dependency'
                dependencyCheckPublisher pattern: 'dependency-check-report.xml'
            }
        }
    }
}
