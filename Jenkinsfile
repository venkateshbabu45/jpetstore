pipeline {
   agent any
   tools
  {  
    jdk 'JAVA_HOME'
    maven 'maven'
       }
      stages
	{
         stage('checkoutstage')
	{
	steps
	{
	  checkout scm
        }
      }
        stage('Build') 
	{
	 steps
         { 
            sh 'mvn clean package -DskipTests'
	     }
	  }
	stage('tomcat warfile deplying')
	{
	steps
	{
         sh 'sudo scp -r /root/kathi.pem /var/lib/jenkins/workspace/petstore/target/jpetstore.war ec2-user@172.31.2.169:/opt/tomcat/apache-tomcat-8.5.54/webapps'

	}
	}	
    }
}
