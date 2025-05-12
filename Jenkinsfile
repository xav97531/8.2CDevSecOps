pipeline{
    agent any 
    stages{
        stage('Build'){
            steps{
                echo "Build started and completed!"
                 }
        }
        stage('Test'){
            steps{
                echo "Test started and completed!"
                 }
        }
        stage('Code quality check'){
            steps{
                echo "Code quality check completed!"
                 }
        }
        stage('Deploy'){
            steps{
                echo "Deployment started and completed!"
                 }
        }
        stage('Approval '){
            steps{
                echo "Approval started and completed!"
                 }
                 timeout(time 3, unit: 'SECONDS')
                 {
                    sleep 5
                 }
        }

        stage('Deploy to Production'){
            steps{
                echo "Deploy to production completed!"
                 }
        }
    }
}