pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t neet95402927/frontend:latest ."
                        // sh "docker build -t adijaiswal/frontend:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t neet95402927/frontend:latest ."
                        // sh "docker push adijaiswal/frontend:latest"
                    }
                }
            }
        }
    }
}
