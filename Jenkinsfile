pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Maven Build') {
            steps {
                echo 'Building Spring Boot application...'
                bat 'mvnw.cmd clean package -DskipTests'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t shiva21sharan/employee-management:jenkins .'
            }
        }

        stage('Docker Login') {
            steps {
                echo 'Docker login will be configured next.'
            }
        }
    }

    post {
        success {
            echo 'CI pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}