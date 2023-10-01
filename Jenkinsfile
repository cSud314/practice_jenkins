#!/usr/bin/env groovy
pipeline{
    agent{ node { label 'default'}}
    environment { 
        PLACE = HOLDER      
    }
    stages {
        stage("Prepare") {
            steps {
                sh "echo pizdec"
                }
        }
        stage("build and push Docker") {
            steps {
                      sh "docker build -t guylurieg/practice:${currentBuild.number} ."
                      withCredentials([usernamePassword(credentialsId: 'Docker User Pass Encrypted', passwordVariable: 'password', usernameVariable: 'username')]) {
                        sh "docker login -u $username -p $password "
                        sh "docker push guylurieg/practice:${currentBuild.number}"
                                                            }
            }
        }
        stage("Finish")
        { steps {
                sh "echo success!!!"
        }
        }

    }
}