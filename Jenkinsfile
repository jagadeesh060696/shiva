pipeline {
    agent any

    environment {
        BRANCH = "${env.BRANCH_NAME}"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "🔁 Checking out branch: ${env.BRANCH_NAME}"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "⚙️ Building branch: ${BRANCH}"
                sh 'echo "Build step running..."'
            }
        }

        stage('Test') {
            steps {
                echo "🧪 Running tests for branch: ${BRANCH}"
                sh 'echo "Test step complete"'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "🚀 Deploying main branch"
                sh 'echo "Deployment successful!"'
            }
        }
    }

    post {
        success {
            echo "✅ Pipeline completed successfully for ${BRANCH}"
        }
        failure {
            echo "❌ Pipeline failed for ${BRANCH}"
        }
    }
}
