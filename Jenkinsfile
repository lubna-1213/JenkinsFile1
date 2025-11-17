pipeline {
    agent any

    environment {
        VERSION = "1.0.5"
    }

    tools {
        maven 'Maven3' // Change 'Maven3' to your Maven tool name in Jenkins dashboard
    }

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building version ${env.VERSION}"
                sh "mvn --version"
                // Maven build command:
                sh "mvn clean install"
            }
        }
        stage('Test') {
            when {
                expression { params.executeTests == true && env.VERSION == "1.0.5" }
            }
            steps {
                echo "Tests Running for version ${env.VERSION}..."
                // Maven test command:
                sh "mvn test"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying version ${env.VERSION}"
                // Your deploy commands go here
            }
        }
    }

    post {
        always {
            echo "Pipeline Finished!"
        }
    }
}
