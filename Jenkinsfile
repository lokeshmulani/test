pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning code from Git...'
                git branch: 'main', url: 'https://github.com/lokeshmulani/test.git'
            }
        }

stage('Deploy to Web Server') {
    steps {
        echo 'Deploying files to Apache root...'
        sh '''
        pwd
        ls -l
        sudo cp index.html /var/www/html/index.html
        sudo chmod 644 /var/www/html/index.html
        '''
    }
}
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed! Check if test/ folder or files exist.'
        }
    }
}
