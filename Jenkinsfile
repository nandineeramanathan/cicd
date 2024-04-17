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
     	environment{
		ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
		user = "${ANYPOINT_CREDENTIALS_USR}"
		password = "${ANYPOINT_CREDENTIALS_PSW}"
		}
      	steps {
        bat 'mvn deploy -DmuleDeploy -Danypoint.username=%user%  -Danypoint.password=%password%' 
      	}
    	}
		
		} 
}