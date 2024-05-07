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
		ANYPOINT_CREDENTIALS = credentials('client_credentials')
		}
      	steps {
		script {
                    println ANYPOINT_CREDENTIALS_USR
					println ANYPOINT_CREDENTIALS_PSW
                }
        bat 'mvn clean deploy -DmuleDeploy -DskipTests -Dclient.id=%ANYPOINT_CREDENTIALS_USR% -Dclient.secret=%ANYPOINT_CREDENTIALS_PSW% -Denv=Sandbox -Ddeployment.region=us-east-2 -Ddeployment.workers=1 -Ddeployment.workerType=MICRO -DappName=mulesoft-cicd-prod12 -Dapp.runtime=4.6.2' 
      	}
    	}
		} 
}