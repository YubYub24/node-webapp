pipeline {
    agent any // Or a specific agent label, e.g., agent { label 'docker-agent' }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image using the Dockerfile in the current directory
                    // 'my-node-app' is the image name, and ':latest' is the tag
                    docker.build('jenkins/jenkins', '.')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Run the built Docker image
                    // '-p 3000:3000' maps container port 3000 to host port 3000
                    // '--name my-running-app' assigns a name to the container
                    // You might need to add a 'docker.withRegistry' block if pushing/pulling from a private registry
                    docker.image('jenkins/jenkins').run('-p 3000:3000 --name my-running-app')
                }
            }
        }

        // Optional: Add a stage to stop and remove the container after testing
        stage('Cleanup Docker Container') {
            steps {
                script {
                    // Stop and remove the container to clean up resources
                    sh 'docker stop my-running-app || true' // Stop if running
                    sh 'docker rm my-running-app || true'  // Remove if exists
                }
            }
        }
    }
}
