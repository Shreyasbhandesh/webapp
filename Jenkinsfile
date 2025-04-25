pipeline {
    agent any
  environment{
       
  }  
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Example: sh 'make build' or your build command
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Example: sh 'make test' or your test command
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Example: Deploy to server via SSH, SCP, or use a deployment tool
                // sh 'scp target/app.jar user@server:/deploy/path/'
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


