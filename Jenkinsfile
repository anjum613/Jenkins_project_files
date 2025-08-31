pipeline {
    agent any

    environment {
        DIRECTORY_PATH = '.' // Relative path since hello.txt is at the root of repository
        TESTING_ENVIRONMENT = 'staging'
        PRODUCTION_ENVIRONMENT = "Anjum Asiya-Production"
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/anjum613/Jenkins_project_files.git', branch: 'main'  // Replace with your repository URL
            }
        }

        stage('Build') {
            steps {
                echo "Fetching source code from: ${env.DIRECTORY_PATH}"
                echo "Compiling the code and generating any necessary artefacts."
                //sh 'ls -l' // List files to verify checkout
            }
        }

        stage('Test') {
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy the application to ${env.TESTING_ENVIRONMENT} environment"
            }
        }

        stage('Approval') {
            steps {
                input message: 'Approve deployment to production?', ok: 'Deploy!'
                sleep 10  // Simulate manual approval for 10 seconds
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploy to production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
