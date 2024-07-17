pipeline {
    agent any
    stages {
        stage('Build Application') {
             steps{
                build job: 'tomcat-java'
            }
        }
        stage('Deploy to Staging Environment'){
            steps{
                build job: 'fromjenkinsfreestyle'
            }            
        }
        stage('Deploy to Production Environment'){
            steps{
                timeout(time:5, unit:'DAYS'){
                    input message:'Approve PRODUCTION Deployment?'
                }
                build job: 'thirdProject'
            }
        }
    }
}
