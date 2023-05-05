pipeline {
    agent any
    environment{
        DIRECTORY_PATH = ' Github Repo '
        TESTING_ENVIRONMENT = ' Plutora '
        PRODUCTION_ENVIRONMENT = ' Digital Ocean '
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
        stage('Test') {
            steps {
                echo 'Jest Test Successful'
                echo 'Jasmine Integration Test Successful'
            }
        }
        stage('Code Quality Check') {
            steps {
                echo 'Check the quality of the code.'
            }
        }
        stage('Deploy') {
            steps {
                echo " Deployed for testing to ${TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                sleep(time: 10, unit: 'SECONDS')
                echo " Approved "
            }
        }
        stage('Deploy to Production') {
            steps {
                echo " Deployed to ${PRODUCTION_ENVIRONMENT} as a Droplet "
            }
        }
    }
}
      
