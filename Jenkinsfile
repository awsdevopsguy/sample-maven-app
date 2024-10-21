pipeline {
    agent any
    
    tools {
        // Use the Maven tool named 'Maven-Project'
        maven 'Maven-Project'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Use the Maven command to compile the project
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                // Use the Maven command to run tests
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Use Maven to package the project
                sh 'mvn package'
            }
        }
    }

    post {
        always {
            // Archive the built artifacts
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
        failure {
            // Send notifications in case of failure
            echo 'Build failed!'
        }
    }
}
