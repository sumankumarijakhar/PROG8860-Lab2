pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sumankumarijakhar/PROG8860-Lab2.git'
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building the project...'
                sh 'python3 main.py'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Running tests...'
                sh 'python3 test_main.py'
            }
        }

        stage('Notify') {
            steps {
                mail to: 'sjakhar5590@conestogac.on.ca',
                     subject: "Jenkins Build Notification",
                     body: "The Jenkins pipeline has completed."
            }
        }
    }
}
