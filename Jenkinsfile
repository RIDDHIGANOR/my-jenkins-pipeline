pipeline {
    agent any
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
    }
}
