pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'java -version'
                sh 'echo "Deepak"'
                sh 'pwd'
                sh 'cd /apigee/Billing && mvn clean compile'
            }
        }
    }
}