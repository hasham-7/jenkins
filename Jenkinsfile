pipeline {
    agent any

    tools {
        maven 'Maven'     // Part 11: Add Build Tools
    }

    environment {
        VERSION = '10.0.1'
    }

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Enable or disable test stage')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn -version'
            }
        }

        stage('Test') {
            when {
                expression { params.executeTests }
            }
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
