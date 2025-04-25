pipeline {
    agent any
  environment{
      DEPLOY_USER = 'ec2-user'
        DEPLOY_HOST = '65.0.11.145'
       
        APP_DIR = '/home/ec2-user/your-app'
        GIT_REPO = 'https://github.com/Shreyasbhandesh/webapp.git'
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                echo 'Building...'
                git clone ${GIT_REPO}
                // Example: sh 'make build' or your build command
                sh'''
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
                sh '''
                echo 'Deploying...'              
                scp -r * ${DEPLOY_USER}@${DEPLOY_HOST}:${APP_DIR}
                ssh ${DEPLOY_USER}@${DEPLOY_HOST} 'cd ${APP_DIR} && ./deploy.sh'
               sh '''
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


