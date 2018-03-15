#!/usr/bin/env groovy

pipeline {
    agent any
    options {
        timestamps()
    }
    stages {
        stage('Build') {
            steps {
                echo("Building project for ")
                sleep(time:5,unit:'SECONDS')
                sh 'mvn clean'
            }
            post {
                success {
                    echo("Build stage completed with result 'SUCCESS'.")
                }
                failure {
                    echo("Build stage completed with result 'FAILURE'.")
                }
            }
        }
        stage('Test') {
            steps {
                echo("Testing project for ")
                sleep(time:5,unit:'SECONDS')
                sh 'mvn package'
            }
            post {
                success {
                    echo("Test stage completed with result 'SUCCESS'.")
                }
                failure {
                    echo("Test stage completed with result 'FAILURE'.")
                }
            }
        }
        stage('install') {
            steps {
                echo("installing project for ")
                sleep(time:5,unit:'SECONDS')
                sh 'mvn install'
            }
            post {
                success {
                    echo("install stage completed with result 'SUCCESS'.")
                }
                failure {
                    echo("install stage completed with result 'FAILURE'.")
                }      
            }
        }
        stage('deploy') {
            steps {
                echo("deploying project for ")
                sleep(time:5,unit:'SECONDS')
                sh 'mvn deploy'
            }
            post {
                success {
                    echo("deploy stage completed with result 'SUCCESS'.")
                }
                failure {
                    echo("deploy stage completed with result 'FAILURE'.")
                }      
            }
        }
    }
    post {
        success {
            echo("Pipeline completed for  with result 'SUCCESS'.")
        }
        failure {
            echo("Pipeline completed for  with result 'FAILURE'.")
        }
    }
}
