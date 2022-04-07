// Run on an agent where we want to use Go
pipeline{
    agent any
    environment{
        root= "/usr/local/go/bin/go"
        scmUrl='https://github.com/zahrul100/sample-go-jenkins.git'
    }
    stages{
        stage("Go Version"){
            steps{
                sh "${root} version"
            }
        }
        stage("Git Clone"){
            steps{
                git url: "${scmUrl}"
            }
        }
        stage("Go Test"){
            steps{
                sh "${root} test ./... -cover"
            }
        }
        stage("Go Build"){
            steps{
                 sh "${root} build ./..."         
            }
        }                        
    }
}