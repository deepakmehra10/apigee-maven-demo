pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'unset JAVA_HOME'
                sh 'mvn --version'
                sh 'java -version'
                sh 'echo "Deepak"'
            }
        }
    }
}