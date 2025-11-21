flag=true

pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'

    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                //using environment variable
                echo"Building Version ${NEW_VERSION}"
            }
        }

        stage('Test') {
            steps {
                when {
                    expression {
                        flag == false
                    }
                }
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
