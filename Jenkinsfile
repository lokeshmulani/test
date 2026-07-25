pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading Source Code'
                git branch: 'main',
                url: 'https://github.com/lokeshmulani/test.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build Started'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Successful'
        }

        failure {
            echo 'Pipeline Failed'
        }
    }
}
