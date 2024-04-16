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
        bat 'mvn deploy -DmuleDeploy -Danypoint.username="${ANYPOINT_CREDENTIALS_USR}"  -Danypoint.password="${ANYPOINT_CREDENTIALS_PSW}"' 
      	}
    	}
		
		} 
}