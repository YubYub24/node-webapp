pipeline {
    agent {
        dockerfile {
            // Specifies the directory containing the Dockerfile, if not at the root
            // dir 'my-docker-app' 
            
            // Specifies a different Dockerfile name if not 'Dockerfile'
            // filename 'Dockerfile.build' 
            
            // Optional: Pass additional build arguments to the docker build command
            // additionalBuildArgs '--build-arg MY_VAR=value'
            
            // Optional: Arguments to pass to the 'docker run' command when running the container
            args '-p 8080:8080' 
        }
    }
    stages {
        stage('Build and Run Docker Container') {
            steps {
                // The agent directive handles the Docker build and run automatically.
                // You can add further steps here to interact with the running container if needed.
                sh 'echo "Docker container built and running on the agent!"'
                // Example: Run a command inside the container
                // sh 'docker exec $(docker ps -q --filter ancestor=<image_id>) ls /app' 
            }
        }
    }
}
