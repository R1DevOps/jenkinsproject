#!groovy
// Check slave properties
properties([disableConcurrentBuilds()])

pipeline {
    agent { 
        label 'master'
        }
    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
    }
     stages {
        stage ('Example') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                sh 'ssh root@10.100.78.214 -p 12908160 \'hotname\''
                sh 'ssh root@10.100.78.214 -p 12908160 \'uptime\''
            }
    }
}
}
