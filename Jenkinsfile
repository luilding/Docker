pipeline {
    agent {
        docker { image 'python:3.8-slim' }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    sh 'docker build -t test-image .'
                }
            }
        }
        stage('Run') {
            steps {
                script {
                    // Run the Docker image
                    sh 'docker run test-image'
                }
            }
        }
    }
}
