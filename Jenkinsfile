pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
                withAWS(region:'us-east-1',credentials:'vijeys3'){
                sh 'aws s3 rm s3://www.naanu.tk --recursive'
                sh 'aws s3 cp public s3://www.naanu.tk --recursive'
                            }
        }
        }
    }
    post{
        always{
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }
    }

}
