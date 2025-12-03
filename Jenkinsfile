pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t neet95402927/loadgenerator:latest ."
                        // sh "docker build -t adijaiswal/loadgenerator:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push neet95402927/loadgenerator:latest"
                        // sh "docker push adijaiswal/loadgenerator:latest"
                    }
                }
            }
        }
    }
}
