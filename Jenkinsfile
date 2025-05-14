pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                sh "echo 'Using npm as the build automation tool to compile and package the Node.js code'"
            }
            post {
                success {
                    mail to: "lauquinne624@gmail.com",
                         subject: "Build Status Email_fix",
                         body: "Build was successful!"
                }
            }
        }
        stage("Unit and Integration Tests") {
            steps {
                sh "echo 'Using Mocha and Chai to conduct unit and integration tests'"
            }
        }
        stage('Code Analysis') {
            steps {
                sh "echo 'Using ESLint to conduct code analysis and ensure it meets industry standards'"
            }
        }
        stage('Security Scan') {
            steps {
                sh "echo 'Using Snyk to identify any vulnerabilities in the code and dependencies'"
            }
        }
        stage('Deploy to Staging') {
            steps {
                sh "echo 'Using SSH to deploy Docker container to the AWS EC2 staging environment'"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                sh "echo 'Using Postman or custom integration scripts to test the staging environment'"
            }
        }
        stage('Deploy to Production') {
            steps {
                sh "echo 'Using SSH to deploy Docker container to the AWS EC2 production environment'"
            }
        }
    }
}
