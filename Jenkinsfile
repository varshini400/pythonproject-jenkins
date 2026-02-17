pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url:'https://github.com/varshini400/pythonproject-jenkins.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("python-app:latest")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("python-app:latest").run("-p 5000:5000")
                }
            }
        }
    }
}
