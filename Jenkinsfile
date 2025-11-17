pipeline {
    agent any

    environment {
        VERSION = "1.0.5"
    }

    tools {
        maven 'Maven_3' // <-- replace with the exact name!
    }

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building version ${env.VERSION}"
                sh "mvn --version"
                sh "mvn clean install"
            }
        }
        stage('Test') {
            when {
                expression { params.executeTests == true && env.VERSION == "1.0.5" }
            }
            steps {
                echo "Tests Running for version ${env.VERSION}..."
                sh "mvn test"
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
