    pipeline {
        agent any
        stages {
            stage('Build') {
                steps {
                    sh 'npm install'
                    sh 'npm run build' // Assuming you have a build script
                }
            }
            stage('Test') {
                steps {
                    sh 'npm test' // Assuming you have a test script
                }
            }
            stage('Deploy') {
                steps {
                    echo 'Deploying application...'
                    // Add your deployment steps here (e.g., pushing to a server)
                }
            }
        }
    }
