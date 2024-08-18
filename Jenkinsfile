pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Dadapeer777/Git_Final_Project'
            }
        }
        stage('Build') {
            steps {
                // Commands to build your project
                sh './build-script.sh'
            }
        }
        stage('Test') {
            steps {
                // Commands to test your project
                sh './test-script.sh'
            }
        }
        stage('Deploy') {
            steps {
                // Commands to deploy your project
                sh './deploy-script.sh'
            }
        }
    }
    post {
        success {
            mail to: 'dadu4299@gmail.com',
                 subject: "SUCCESS: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                 body: "Great news! The build #${env.BUILD_NUMBER} was successful."
        }
        failure {
            mail to: 'dadu4299@.com',
                 subject: "FAILURE: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                 body: "Unfortunately, the build #${env.BUILD_NUMBER} failed."
        }
    }
}
