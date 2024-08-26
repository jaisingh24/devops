pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: '<>'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // You can add more build steps here if needed
            }
        }

        stage('Test') {
            steps {
                echo 'Testing the project...'
                // Add your test scripts here
            }
        }

        stage('Deploy') {
            steps {
                sshagent(['your-ssh-credentials-id']) {
                    sh 'scp -r * user@your-public-ip:/var/www/html/'
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
