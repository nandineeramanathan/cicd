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
        bat 'mvn deploy -P cloudhub -Dmule.version=4.5.1 -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW}' 
      	}
    	}
		
		} 
}