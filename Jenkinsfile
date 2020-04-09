pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'java -version'
                sh 'echo "Deepak"'
                sh 'pwd'
                sh 'unset JAVA_HOME'
                sh 'unset JAVA_HOME && cd ./apigee/Billing && mvn clean compile'
            }
        }
    }
}