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
                "ssh root@localhost hostname"
            }
        }
        stage("Second step") {
            steps {
                "ssh root@localhost uptime"
            }
        }
    }
}
