pipeline{
    agent{
        label 'incm-agemt'
    }
    stages{
        stage('Checkout'){
            steps{
                sh "./checkout-repos.sh"
            }
        }
    }
}