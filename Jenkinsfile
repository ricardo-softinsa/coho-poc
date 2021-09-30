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
                sh "cd ${WORKSPACE} && cppcheck --enable=all --inconclusive --xml --xml-version=2 ${WORKSPACE} 2> cppcheck-results.xml"
            }
        }
        stage("CppCheck - Publish"){
            steps{
                publishCppcheck displayErrorSeverity: true, pattern: 'cppcheck-results.xml', displayNoCategorySeverity: true, displayPerformanceSeverity: true, displayPortabilitySeverity: true, displayStyleSeverity: true, displayWarningSeverity: true, failureThreshold: '10', healthy: '5', ignoreBlankFiles: true, newFailureThreshold: '5', newThreshold: '10', numBuildsInGraph: 10, threshold: '20', unHealthy: '5'
                //publishCppcheck pattern: 'cppcheck-results.xml'
                echo "teste"
            }
        }
    }
    post{
        always{
            deleteDir()
        }
    }
}