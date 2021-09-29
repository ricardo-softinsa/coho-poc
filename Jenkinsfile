pipeline{
    agent{
        label 'incm-agent'
    }
    stages{
        stage('Checkout'){
            steps{
                sh "./checkout-repos.sh"
            }
        }
    }
}