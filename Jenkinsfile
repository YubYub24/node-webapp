pipeline {
    agent any // Or specify a label for a specific agent: agent { label 'my-docker-agent' }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image from the Dockerfile in the current directory
                    // Replace 'my-image' and 'latest' with your desired image name and tag
                    docker.build('jenkins/jenkins')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Run the built Docker image as a container
                    // Replace 'my-image' and 'latest' with your image name and tag
                    // Add any necessary port mappings or volume mounts here
                    docker.image('jenkins/jenkins').run('-p 8080:8080')
                }
            }
        }
    }

    post {
        always {
            // Clean up any running containers or images if necessary
            script {
                // Optional: Stop and remove the container after the pipeline completes
                // docker.image('my-image:latest').stop()
                // docker.image('my-image:latest').remove()
            }
        }
    }
}
