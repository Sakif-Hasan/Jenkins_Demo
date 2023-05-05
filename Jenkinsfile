pipeline {
    agent any

    environment{
        DIRECTORY_PATH = ' Github '
        TESTING_ENVIRONMENT = ' AWS Elastic Beanstalk '
        PRODUCTION_ENVIRONMENT = ' AWS Elastic Compute Cloud '
    }
    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the ${DIRECTORY_PATH}."
                echo ' Building .... '
            }
            post{
                success{
                    mail to: "sakifhasan.work@gmail.com",
                    subject: "Jenkins Build Status Email",
                        body: " Build Successful "
                }
            }
        }
        stage('Unit & Integration Test') {
            steps {
                echo 'Jest Test Successful'
                echo 'Jasmine Integration Test Successful'
            }
        }
        stage('Code Analysis') {
            steps {
                echo ' Embold Code Review Successful '
            }
        }
        stage('Security Scan') {
            steps {
                echo " AWS Inspector Review Succecssful "
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo " Application Staged in AWS Elastic Beanstalk Successfully "
            }
        }
        stage('Integration Test Staging') {
            steps {
                echo 'AWS Elastic Beanstalk Integration Test Successful'
                echo " Approved "
            }
        }
        stage('Deploy to Production') {
            steps {
                echo " Deployed to ${PRODUCTION_ENVIRONMENT} "
            }
        }
        stage("Console Log"){
            steps {
                //echo "${BUILD_URL}/consoleText"
                script{
                    def consoleLog = ${BUILD_URL}/consoleText
                }
                echo consoleLog
            }
        }
    }
}
      
