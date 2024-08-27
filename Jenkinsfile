pipeline {
	agent any 
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			git 'https://github.com/adityawalke-git/GRRAS-1.git'			       
		      }}
		stage('Build') {
	           steps {
			  sh 'mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		   script {
		   sh '''if ( env.ENVIRONMENT == \'QA\' ){
		   sh \'cp target/GRRAS-1.war /home/aditya/Documents/apache-tomcat-9.0.88/webapps\'
		   echo "deployment has been done on QA!"
		   }
		   elif ( env.ENVIRONMENT == \'UAT\' ){
		   sh \'cp target/GRRAS-1.war /home/aditya/Documents/apache-tomcat-9.0.88/webapps\'
		 echo "deployment has been done on QA!"
		 }
		 echo "deployment has been done!"
			fi'''
			}}}  
			
}}
