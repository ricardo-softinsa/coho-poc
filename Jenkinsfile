pipeline{
    agent{
        label 'incm-agent'
    }
    stages{
        stage('Checkout'){
            steps{
                sh "chmod 777 checkout-repos.sh"
                sh "./checkout-repos.sh"
            }
        }
    }
}