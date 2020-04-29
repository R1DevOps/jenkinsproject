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
        stage("First step") {
            steps {
                println "hostname"
            }
        }
        stage("Second step") {
            steps {
                sh 'ssh root@localhost \'uptime\''
            }
        }
    }
}
