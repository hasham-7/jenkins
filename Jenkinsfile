flag=true

pipeline {
    agent any
       parameters {
               string(name: 'VERSION', defaultvalue: '', description: 'version to deploy on prod')
               choice(name: 'VERSION', choices:['1.1.0','1.2.0','1.3.0'],description:'')
               booleanParam(name: 'executeTests', defaultvalue: true, description: '')
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
                //using environment variable
                echo"Building Version ${NEW_VERSION}"
                sh "nvm install"
            }
        }

        stage('Test') {
               when (
                       expression (
                               params.executeTests
                           }
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
