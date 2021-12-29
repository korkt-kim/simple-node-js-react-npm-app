pipeline {
    agent any
    tools {nodejs "NodeJS-14.13.1"}
    
    environment {
        CI = 'true'
    }

    stages {
        stage('Build') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test'){
            steps {
                bat """
                    cd jenkins/scripts/
                    dir /a /b
                    test.bat
                """
            }
        }

        stage('Deliver') {
            steps {
                bat """
                    cd jenkins/scripts
                    dir /a /b
                    deliver.bat
                """
            }
        }
    }
}
