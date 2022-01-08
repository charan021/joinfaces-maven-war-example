pipeline {
	agent { label 'jenkins' }
    stages {
	    
       stage('checkout') {
            steps {
                sh 'sudo rm -rf joinfaces-maven-war-example'
	sh 'git clone https://github.com/joinfaces/joinfaces-example-war.git'	
              }
        }
	 stage('build') {
	
            steps {
                dir('joinfaces-maven-war-example'){
                  sh 'pwd'
                sh 'ls'
            
                sh 'docker build -t tomcat:ver1.1 .'  
                }
              
                
            }
	 }
	 stage('deploy'){
	     steps{
	        sh 'docker rm -f mytomcat'
	         sh 'docker run -d --name mytomcat -p 7777:8080 tomcat:ver1.1'
	     }
	 }
    }
}
