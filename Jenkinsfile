pipeline {
	agent any 
	
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
		sh 'cp target/GRRAS-1.war /home/aditya/Documents/apache-tomcat-9.0.88/webapps'
			}}	
}}
