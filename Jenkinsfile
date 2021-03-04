pipeline {	 
	agent any	 
    	stages {     	 
    		stage("Compile") {          	 
            		steps {               	 
                		sh "mvn compile"          	 
            		}     	 
        	}     	 
    		stage("Unit test") {          	 
        		steps {               	 
                		sh "mvn test"          	 
            		}     	 
        	}	 
    		stage("Deploy in tomcat AWS") {          	 
        		steps { 
				sshagent(['deploy_user_new']){
				sh "scp -o StrictHostKeyChecking=no target/BookzyWebApp-0.0.1-SNAPSHOT.war ubuntu@ec2-100-25-38-44.compute-1.amazonaws.com:/opt/tomcat/webapps"   	 
				}           
            		}     	 
        	}	 
    	}
}
