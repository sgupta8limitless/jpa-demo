pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/sgupta8limitless/jpa-demo']])
            }
        }


        stage('Build') {
            steps {
                bat "mvn clean install -DskipTests"
            }
        }


        stage('Deploy') {
            steps {
                bat "docker compose up --build"
            }
        }
    }
}
