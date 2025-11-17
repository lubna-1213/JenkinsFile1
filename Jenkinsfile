
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing..'
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
    stage('Test') {
    when {
        expression { return true }  // add your condition
    }
    steps {
        echo 'Conditional Testing..'
    }
}

}

