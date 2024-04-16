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
        bat 'mvn deploy -DmuleDeploy -Danypoint.username=${ANYPOINT_CREDENTIALS_USR}  -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW} -Denv=Sandbox  -Ddeployment.region=us-east-2 -Ddeployment.workers=1 -Ddeployment.workerType=MICRO -DappName=mulesoft-cicd-sample1 -Dapp.runtime=4.6.2' 
      	}
    	}
		
		} 
}