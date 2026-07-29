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
                echo 'Deploying files from test directory to Apache root...'
                // If you just have index.html inside test/:
                sh 'cp /home/ec2-user/test/index.html /var/www/html/index.html'
                
                // OR if you have multiple files/folders inside test/ (images, CSS, JS):
                // sh 'cp -r test/* /var/www/html/'
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
