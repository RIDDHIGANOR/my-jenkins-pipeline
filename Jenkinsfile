pipeline {
    agent any
    tools{nodejs "mynodejs"}
    stages {
        stage('Hello 1') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Dev') {
            steps {
                git 'https://github.com/RIDDHIGANOR/my-jenkins-pipeline.git'
                echo 'Hello Dosto'
                sh 'cat README.md'
            }
        }
        stage('node build') {
            steps {
                sh 'npm install'
            }
        }
         stage('Saving artifacts') {
            steps {
               archiveArtifacts artifacts: '**', followSymlinks: false
            }
        }
        stage('Stage with secret') {
            environment{
                NODE_ENV = "stage"
            }
            steps {
               withCredentials([string(credentialsId: 'mysecrettext', variable: 'production_secret')]) {
               echo "${production_secret}"
               script{
               println "The secret value is : ${production_secret}"
               }
            }
            }
        }
    }
}
