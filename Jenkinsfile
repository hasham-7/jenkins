pipeline {
    agent any

    tools {
        maven 'Maven'  // This should match the Maven installation name in Jenkins Global Tool Configuration
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
                // Clean previous builds and compile the project
                sh 'mvn clean compile'
                // Or package into a JAR if needed
                sh 'mvn package'
            }
        }

        stage('Test') {
            when {
                expression { params.executeTests }
            }
            steps {
                echo 'Running Tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                echo "Version ${VERSION}"
                // Example: copy jar to some directory or deploy somewhere
                // sh 'cp target/my-app-1.0-SNAPSHOT.jar /path/to/deploy/'
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
