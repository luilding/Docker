pipeline {
    agent {
        docker {
            image 'python:3.8-slim'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    //Change directory path to Unix-style format
                    def workspaceUnix = pwd().replace('\\', '/')
                    
                    //Build the Docker image using the Unix-style path
                    sh "docker build -t test-image ${workspaceUnix}"
                }
            }
        }
        stage('Run') {
            steps {
                script {

                    sh "docker run test-image"
                }
            }
        }
    }
}

