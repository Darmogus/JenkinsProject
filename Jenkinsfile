pipeline {
    agent any
    tools {
        maven 'MavenTool'
    }
    
    stages {
        stage("build") {
            steps {
                sh 'mvn -v'
            }
        }
        
        stage("test") {
            steps {
                echo 'Running tests'
            }
        }
        
        stage("deploy") {
            steps {
                echo 'Deploying application'
            }
        }
    }
}
