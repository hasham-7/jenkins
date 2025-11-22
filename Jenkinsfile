pipeline {
    agent any

    tools {
        maven 'Maven'     // ← Part 11: Add Build Tools (Maven)
    }

    environment {
        VERSION = '10.0.1'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn -version'   // optional: verify Maven
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
        always {
            echo 'Pipeline Completed'
        }

        failure {
            echo 'Post Action if Build Failed'
        }
    }
}
