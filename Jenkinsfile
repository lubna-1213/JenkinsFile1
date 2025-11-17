pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            when {
                expression { return true } // Replace with your condition
            }
            steps {
                echo 'Conditional Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {
        always {
            echo "Pipeline Finished!"
        }
    }
}
