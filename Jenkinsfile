pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo '📥 Checking out the source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo '🔨 Building the project...'
                // Build step
                sh './gradlew assemble'
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Running the tests...'
                // Test step
                sh './gradlew test'
            }
        }
    }

    post {
        success {
            echo '✅ Build and tests completed successfully!'
        }
        failure {
            echo '❌ Build or tests failed!'
        }
    }
}
