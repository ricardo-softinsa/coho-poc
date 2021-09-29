pipeline{
    agent{
        label 'incm-agent' 
    }
    stages{
        stage('CppCheck - Analysis'){
            environment{
                source_dir="/home/jenkins/workspace/incm-poc"
            }
            steps{
                sh "cd ${source_dir} && cppcheck --enable=all --inconclusive --xml --xml-version=2 ${source_dir} 2> cppcheck.xml"
            }
        }
        stage("CppCheck - Publish"){
            steps{
                publishCppcheck failureThreshold: '10', healthy: '5', ignoreBlankFiles: true, newFailureThreshold: '5', newThreshold: '10', threshold: '20', unHealthy: '5'
                echo "teste"
            }
        }
    }
}