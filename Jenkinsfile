pipeline {
    agent any

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
            }
        }
    }

    post {
        // This always runs
        always {
            echo 'Post build condition running'
        }

        // This runs only if the build fails
        failure {
            echo 'Post Action if Build Failed'
        }
    }
}
