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
                sh 'ssh root@10.100.78.214 \'hostname\''
                sh 'ssh root@10.100.78.214 \'uptime\''
                sh 'ssh root@10.100.78.214 \'rm -rf /tmp/var\''
               
            }
        }
     }
stage("send index.html to www/html on serv") {
            steps {
                echo " ============== start to send =================="
                dir ('R1DevOps/web') {
                	sh 'cp index.html /var/www/html '
                }
            }
         }
     }
