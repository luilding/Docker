pipeline {
    agent none
    stages {
        stage('Build and Run') {
            agent {
                docker {
                    image 'python:3.8-slim'
                    args '-v /var/run/docker.sock:/var/run/docker.sock'
                }
            }
            steps {
                script {
                    // Convert Windows-style path to Unix-style path for Docker
                    def workspaceUnix = pwd().replace('\\', '/').replace('C:', '/c')
                    
                    // Build the Docker image using the Unix-style path
                    sh "docker build -t test-image ${workspaceUnix}"

                    // Run the Docker image
                    sh "docker run test-image"
                }
            }
        }
    }
}
