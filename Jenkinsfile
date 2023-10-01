#!/usr/bin/env groovy
pipeline{
    agent{ node { label 'aws-example'}}
    environment { 
        A = B
    }
    stages {
        stage("Prepare") {
            bitbucketStatusNotify buildState: "INPROGRESS"
        }
    }
}