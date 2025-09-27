// Jenkinsfile

pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("birthday-site:${env.BUILD_NUMBER}")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    dockerImage.run("-d -p 8080:80")
                }
            }
        }
    }
}
