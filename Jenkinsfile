pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
                withAWS(region:'us-east-1',credentials:'vijeys3'){
                sh 'aws s3 rm s3://vijeys3 --recursive'
                sh 'aws s3 cp public s3://vijeys3 --recursive'
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
