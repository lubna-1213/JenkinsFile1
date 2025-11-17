pipeline {
    agent any

    environment {
        VERSION = "1.0.5"
    }

    stages {
        stage('Build') {
            steps {
                echo "Building version ${env.VERSION}"
            }
        }
        stage('Test') {
            when {
                expression { env.VERSION == "1.0.5" }
            }
            steps {
                echo "Testing only for version ${env.VERSION}"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying version ${env.VERSION}"
            }
        }
    }

    post {
        always {
            echo "Pipeline Finished!"
        }
    }
}
