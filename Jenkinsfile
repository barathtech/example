pipeline {
    agent any
    tools {
        go 'go1.18'
    }
    environment {
        GO114MODULE = 'on'
        CGO_ENABLED = 0 
        GOPATH = "${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"
    }
    stages {        
        stage('Pre Test') {
            steps {
                echo 'Installing dependencies'
                sh 'go version'
                sh 'go get -u golang.org/x/lint/golint'
            }
        }
        
        stage('Build') {
            steps {
               git url: 'https://github.com/barathtech/example.git'    
            }
        }

        stage('Test') {
            steps {
                sh 'apt install gccgo-go -y'
                }
            }
        }        
    }
