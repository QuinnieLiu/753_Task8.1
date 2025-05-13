pipeline{
    agent any
    environment{
        DIRECTORY_PATH = '/Users/qingliu/T1'
        TESTING_ENVIRONMENT = 'staging'
        PRODUCTION_ENVIRONMENT = 'QuinnieLiu'
    }
    stages{
        stage("Build"){
            steps{
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artefacts"
            }
            post{
                success{
                    mail to: "lauquinne624@gmail.com",
                    subject: "Build Status Email",
                    body: "Build was successful!"
                }
            }
        }
        stage("Test"){
            steps{
                echo "Unit tests"
                echo "Integration tests"
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep(time: 10, unit: 'SECONDS')
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }

    }
}