pipeline {
    agent any          // Le pipeline peut s'exécuter sur n'importe quel agent Jenkins.
    
    stages {
        stage("build") {   // Étape "build"
            steps { 
                echo 'Building the application'  // Action : afficher un message dans la console.
            }
        }
        
        stage("test") {    // Étape "test"
            steps { 
                echo 'Testing the application'  // Action : afficher un message dans la console.
            }
        }
        
        stage("deploy") {  // Étape "deploy"
            steps { 
                echo 'Deploying the application'  // Action : afficher un message dans la console.
            }
        }
    }
}
