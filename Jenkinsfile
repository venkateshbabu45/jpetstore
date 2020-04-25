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
         sh 'sudo scp -i -r /root/kathi.pem /var/lib/jenkins/workspace/petstore/target/jpetstore.war ec2-user@ec2-52-66-243-142.ap-south-1.compute.amazonaws.com:~/opt/tomcat/apache-tomcat-8.5.54/webapps'

	}
	}	
    }
}
