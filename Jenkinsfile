pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Getting source code from GitHub'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building Maven project'
                bat 'mvn -B clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running test cases'
                bat 'mvn -B test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging application'
                bat 'mvn -B package'
            }
        }
    }

    post {
        success {
            echo 'PIPELINE EXECUTED SUCCESSFULLY!'
        }
        failure {
            echo 'PIPELINE FAILED!'
        }
    }
}
