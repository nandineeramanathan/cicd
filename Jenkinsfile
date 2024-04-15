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
     	environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      	}
      	steps {
        bat 'mvn deploy -DmuleDeploy  -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW}' 
      	}
    	}
		
		} 
}
