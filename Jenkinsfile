pipeline
{
	agent any 
	stages{ 
	
		stage('Build Application') { 
		steps { 
		bat 'mvn clean install' 
		} 
		}
		
		stage('Deploy CloudHub') { 
     	
      	steps {
        bat 'mvn deploy -P arm -Darm.target.name=4.5.0 -DmuleDeploy -Danypoint.username=${ANYPOINT_CREDENTIALS_USR}  -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW}' 
      	}
    	}
		
		} 
}