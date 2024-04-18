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
		}
      	steps {
        bat 'mvn clean deploy -DmuleDeploy -DskipTests -Danypoint.username=nandinee2 -Danypoint.password=Helloworld@123 -Denv=Sandbox -Ddeployment.region=us-east-2 -Ddeployment.workers=1 -Ddeployment.workerType=MICRO -DappName=mulesoft-cicd-sample1 -Dapp.runtime=4.6.2' 
      	}
    	}
		} 
}