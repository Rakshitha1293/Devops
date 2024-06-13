pipeline {
    agent any

    environment {
        // Define any environment variables if needed
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git branch: 'main', url: 'https://github.com/Rakshitha1293/Devops.git'
            }
        }

        stage('Build') {
            steps {
                // Example: Compile the application
                sh './gradlew build'  // For a Gradle project
                // sh 'mvn clean package'  // For a Maven project
            }
        }

        stage('Test') {
            steps {
                // Example: Run unit tests
                sh './gradlew test'  // For a Gradle project
                // sh 'mvn test'  // For a Maven project
            }
        }

        stage('Deploy') {
            steps {
                // Example: Deploy the application
                // This could involve copying files, running scripts, etc.
                sh 'scp -r ./build/libs/*.jar user@server:/path/to/deploy'
            }
        }
    }

    post {
        always {
            // Actions to always perform, such as cleanup
            cleanWs()
        }
        success {
            // Actions to perform on successful completion
            echo 'Pipeline completed successfully!'
        }
        failure {
            // Actions to perform on failure
            echo 'Pipeline failed!'
        }
    }
}
