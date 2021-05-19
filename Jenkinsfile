properties([pipelineTriggers([githubPush()])])
 
pipeline {
    /* specify nodes for executing */
    agent any
 
    stages {
        /* checkout repo */
        stage('Checkout SCM') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: [[name: 'devops']],
                 userRemoteConfigs: [[
                    url: 'git@github.com:veekrum/simple-python-pyinstaller-app.git',
                    credentialsId: '',
                 ]]
                ])
            }
        }
         stage('Do the deployment') {
            steps {
                echo ">> Run deploy applications "
            }
        }
    }
 
    /* Cleanup workspace */
    post {
       always {
           deleteDir()
       }
   }
}
