pipeline {
	agent any 
	parameters {
  choice choices: ['DEV', 'QA', 'UAT'], name: 'ENVIRONMENT '
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
			sh '''if [ $ENVIRONMENT = "QA" ];then
         cp target/GRRAS-1.war /home/aditya/Documents/apache-tomcat-9.0.88/webapps     
elif  [ $ENVIRONMENT = "UAT" ];then
         cp target/GRRAS-1.war /home/aditya/Documents/apache-tomcat-9.0.88/webapps
echo "deployment has been done!"
fi'''
			}}}  
			
}}
