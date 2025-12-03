pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh "docker build -t neet95402927/adservice:latest ."
                        // sh "docker build -t adijaiswal/adservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh "docker push neet95402927/adservice:latest "
                        // sh "docker push adijaiswal/adservice:latest "
                    }
                }
            }
        }
    }
}
