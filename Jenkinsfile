pipeline { 
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh "docker build -t neet95402927/shippingservice:latest ."
                        // sh "docker build -t adijaiswal/shippingservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh "docker push neet95402927/shippingservice:latest "
                        // sh "docker push adijaiswal/shippingservice:latest "
                    }
                }
            }
        }
    }
}
