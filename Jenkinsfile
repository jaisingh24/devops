pipeline {
    agent any

    stages {
        
        

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
                sshagent(['my-ec2-ssh']) {
                    sh 'scp -r * user@http://54.162.178.100/:/var/www/html/'
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
