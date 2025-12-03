pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t neet95402927/currencyservice:latest ."
                        // sh "docker build -t adijaiswal/currencyservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push neet95402927/currencyservice:latest "
                        // sh "docker push adijaiswal/currencyservice:latest "
                    }
                }
            }
        }
    }
}
