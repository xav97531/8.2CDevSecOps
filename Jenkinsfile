pipeline {
    agent any 

    environment {
        JOB_URL = "http://localhost:8080/job/CD-Pipeline"
        TESTING_ENVIRONMENT = "Pipeline"
        STAGING_ENVIRONMENT = "Staging Server"
        PRODUCTION_ENVIRONMENT = "Production Server"
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from $JOB_URL"
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests..."
                echo "Running integration tests..."
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Performing code quality analysis..."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing security scan and checking for vulnerabilities..."
            }
            post {
                always {
                    mail to: 'xadams130@gmail.com',
                         subject: "🔍 Security Scan Result - Build #${env.BUILD_NUMBER}",
                         body: "The Security Scan stage has finished. Please check Jenkins for the result of build #${env.BUILD_NUMBER}."
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to $STAGING_ENVIRONMENT..."
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment..."
            }
            post {
                always {
                    mail to: 'xadams130@gmail.com',
                         subject: "🧪 Staging Test Result - Build #${env.BUILD_NUMBER}",
                         body: "Integration tests on staging have finished. Please check Jenkins for the result of build #${env.BUILD_NUMBER}."
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to $PRODUCTION_ENVIRONMENT..."
            }
        }
    }

    post {
        always {
            mail to: 'xadams130@gmail.com',
                 subject: "📦 Pipeline Complete - Build #${env.BUILD_NUMBER}",
                 body: "The entire pipeline has finished. Please check Jenkins for full details of build #${env.BUILD_NUMBER}."
        }
    }
}
