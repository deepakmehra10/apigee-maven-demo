pipeline {
    agent any
    stages {
        stage('build') {
            steps {
            script {
                      withCredentials([
                        usernamePassword(credentialsId: 'apigee-credentials',
                          usernameVariable: 'username',
                          passwordVariable: 'password')
                      ]) {
                        print 'username=' + username + 'password=' + password
                        print 'username.collect { it }=' + username.collect { it }
                                    print 'password.collect { it }=' + password.collect { it }
                 sh('java -version')
                 sh "echo ${username}.collect { it }"
                 environment = "test"
                 println("mvn clean install -P${environment} -Dusername=${username} -Dpassword=${password} -Doptions=override")
                 test = env.getEnvironment()
                 println(test)
                      }
                    }

                sh "echo ${username}"
                sh 'echo "Deepak"'
                sh 'pwd'
                sh 'unset JAVA_HOME'
                sh 'unset JAVA_HOME && cd ./apigee/Billing && mvn clean compile'
            }
        }
    }
}
