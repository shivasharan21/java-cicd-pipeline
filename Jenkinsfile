pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building Employee Management application...'
                bat 'mvnw.cmd clean package -DskipTests'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t employee-management:jenkins .'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}