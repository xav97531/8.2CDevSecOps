pipeline {
    agent any 
    environment {
        DIRECTORY_PATH = "http://localhost:8080/job/CD-Pipeline"
        TESTING_ENVIRONMENT = "Pipeline"
        PRODUCTION_ENVIRONMENT = "Xavier"
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from $DIRECTORY_PATH"
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Check the quality of the code!"
            }
        }

        stage('Security Scan') {
            steps {
                echo "Scanning the security of the code and checking for vulnerabilities"
            }
            post {
                success {
                    emailext (
                        to: 'xadams130@gmail.com',
                         subject: 'Security Scan: SUCCESS',
                         body: 'Security Scan stage completed successfully.'
                        attachlog true 
                    )
                }
                failure {
                    mail to: 'xadams130@gmail.com',
                         subject: 'Security Scan: FAILURE',
                         body: 'Security Scan stage failed. Check Jenkins logs for more details.'
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploy the application to $PRODUCTION_ENVIRONMENT"
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment..."
            }
            post {
                success {
                    mail to: 'xadams130@gmail.com',
                         subject: 'Staging Integration Tests: SUCCESS',
                         body: '✅ Integration tests on staging completed successfully.'
                }
                failure {
                    mail to: 'xadams130@gmail.com',
                         subject: 'Staging Integration Tests: FAILURE',
                         body: '❌ Integration tests on staging failed. Check Jenkins logs for more details.'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to $PRODUCTION_ENVIRONMENT!"
            }
        }
    }
}
