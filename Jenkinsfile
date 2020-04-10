pipeline {
    agent any
    stages {
        stage('build') {
         when{
            branch 'master'
          }
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
                 sh 'unset JAVA_HOME && cd ./apigee/Billing && mvn clean install -P${environment} -Dusername=${username} -Dpassword=${password} -Doptions=override'
                 branch_name = env.BRANCH_NAME
                 println(branch_name)
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
