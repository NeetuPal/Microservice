pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {

                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh "docker build -t neet95402927/cartservice:latest ."
                        // sh "docker build -t adijaiswal/cartservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh "docker push neet95402927/cartservice:latest "
                        // sh "docker push adijaiswal/cartservice:latest "
                    }
                }
            }
        }
    }
}
