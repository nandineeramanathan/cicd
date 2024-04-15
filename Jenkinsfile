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
        bat 'mvn deploy -DmuleDeploy' 
      	}
    	}
		
		} 
}