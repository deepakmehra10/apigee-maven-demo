pipeline {
    agent any
    stages {
        stage('build') {
            steps {
            script {
                      withCredentials([
                        usernamePassword(credentialsId: 'gitlab',
                          usernameVariable: 'username',
                          passwordVariable: 'password')
                      ]) {
                        print 'username=' + username + 'password=' + password
                      }
                    }
                sh 'java -version'
                sh 'echo "Deepak"'
                sh 'pwd'
                sh 'unset JAVA_HOME'
                sh 'unset JAVA_HOME && cd ./apigee/Billing && mvn clean compile'
            }
        }
    }
}
