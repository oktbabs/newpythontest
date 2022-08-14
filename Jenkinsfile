pipeline {
    agent any
      environment {
                           DOCKER_HOME='/usr/bin/docker'
      }
       
 
 
    stages {   
      
    stage('git clone repo') {
            steps {
                git branch: 'master', credentialsId: 'oktbabs', url: 'https://github.com/oktbabs/newpythontest.git'

            }
        }
 stage('execute python script') {
            steps {
                sh '''python server.py'''

            }
        }
    }
	
}
