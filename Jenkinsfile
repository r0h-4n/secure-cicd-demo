pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checked out from GitHub'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'SonarScanner'

                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=Secure-CICD-Demo -Dsonar.sources=."
                    }
                }
            }
        }

        stage('Pipeline Completed') {
            steps {
                echo 'CI/CD Pipeline executed successfully!'
            }
        }
    }
}
