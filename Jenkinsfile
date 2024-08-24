pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the repository
                checkout scm
            }
        }
        stage('Run Python Script') {
            steps {
                // Run the Python script
                script {
                    bat 'python hello.py' // Use 'sh' instead of 'bat' if running on a Unix-based system
                }
            }
        }
    }
}
