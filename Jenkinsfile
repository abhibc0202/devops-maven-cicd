pipeline {
    agent any

    tools {
        maven 'Maven-3.9.12'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Create ZIP') {
            steps {
                sh 'zip -j devops-project.zip index.html'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'devops-project.zip', fingerprint: true
        }
    }
}
