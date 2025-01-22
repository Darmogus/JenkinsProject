pipeline {
    agent none
    
    tools {
        maven 'maven 3.8.7'  // Spécification de la version de Maven à utiliser
    }

    stages {
        stage('Check Maven Path') {
            agent any
            steps {
                script {
                    // Vérification que Maven est installé et dans le PATH
                    sh 'which mvn || echo "Maven is not found"'
                }
            }
        }

        stage('Checkout from Git') {
            agent any
            steps {
                script {
                    // Clonage du dépôt Git et vérification de la structure des fichiers
                    checkout scm
                }
            }
        }

        stage('Build and Analysis with SonarQube') {
            agent any
            steps {
                script {
                    // Exécution de la commande Maven pour construire et analyser avec SonarQube
                    sh 'mvn clean package sonar:sonar'
                }
            }
        }
    }
}
