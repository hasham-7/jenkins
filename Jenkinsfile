pipeline {
    agent any

    environment {
        VERSION = '10.0.1'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                echo "Version ${VERSION}"
            }
        }
    }

    post {
        // This always runs
        always {
            echo 'Pipeline Completed'
        }

        // This runs only if the build fails
        failure {
            echo 'Post Action if Build Failed'
        }
    }
}
