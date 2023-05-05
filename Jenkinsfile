pipeline {
    agent any
    environment{
        DIRECTORY_PATH = ' PATH '
        TESTING_ENVIRONMENT = ' TEST ENV '
        PRODUCTION_ENVIRONMENT = ' Sakif_Hasan '
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
                echo 'Unit Test'
                echo 'Integration Test'
            }
        }
        stage('Code Quality Check') {
            steps {
                echo 'Check the quality of the code.'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment ${TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                sleep(time: 10, unit: 'SECONDS')
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploy to Code to the Production Environment ${PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
      
