pipeline{
    agent any 
    environment {
        DIRECTORY_PATH= "http://localhost:8080/job/CD-Pipeline"
        TESTING_ENVIRONMENT= "Pipeline"
        PRODUCTION_ENVIRONMENT= "Xavier"
    }
    stages{
        stage('Build'){
            steps{
                echo "Fetch the source code from $DIRECTORY_PATH"
                 }
        }
        stage('Unit and Integration Tests'){
            steps{
                echo "Unit tests"
                echo "Integration tests"
                 }
        }
        stage('Code Analysis'){
            steps{
                echo "Check the quality of the code!"
                 }
        }
        stage('Security Scan'){
            steps{
                echo "Scanning the security of the code and checking for vulnerabilities"
                 }
        }
        stage('Deploy to Staging'){
            steps{
                echo "Deploy the application to $PRODUCTION_ENVIRONMENT"
                 }
        }
         stage('integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment..."
                sleep time: 10, unit: 'SECONDS'
            }
        }

        stage('Deploy to Production'){
            steps{
                echo "Deploying the code to $PRODUCTION_Environment !"
                 }
        }
        
    }
}
