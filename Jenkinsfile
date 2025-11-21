flag = true

pipeline {
    agent any

    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Version to deploy')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
    }

    tools {
        maven 'Maven'
    }

    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                echo "Building Version ${NEW_VERSION}"
                sh "nvm install"
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
            }
        }
    }

    post {
        always {
            echo 'Post build condition running'
        }

        failure {
            echo 'Post Action if Build Failed'
        }
    }
}
