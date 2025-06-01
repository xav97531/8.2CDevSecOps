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
        stage('Test'){
            steps{
                echo "Unit tests"
                echo "Integration tests"
                 }
        }
        stage('Code quality check'){
            steps{
                echo "Check the quality of the code!"
                 }
        }
        stage('Deploy'){
            steps{
                echo "Deploy the application to $PRODUCTION_ENVIRONMENT"
                 }
        }
         stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep time: 10, unit: 'SECONDS'
            }
        }

        stage('Deploy to Production'){
            steps{
                echo "Deploying the code to $PRODUCTION_Environment !"
                 }
        }

stage('Done'){
            steps{
                echo "Done the code to $PRODUCTION_Environment !"
                 }
        }
        
    }
}
