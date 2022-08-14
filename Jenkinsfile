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
  
     stage("Docker login"){
      steps{
         withCredentials([usernamePassword(credentialsId: 'oktbabs', passwordVariable: 'DOCKER_PASS', usernameVariable: 'DOCKER_USER')]){
      sh "echo  ${DOCKER_PASS} |sudo ${DOCKER_HOME} login -u ${DOCKER_USER} --password-stdin"
            }
        }
   }
    stage('Docker build') {
            steps {
                sh "sudo ${DOCKER_HOME} build -t oktbabs/newpytest:v1.0.0 ."

            }
        }	    
    }
	
}
