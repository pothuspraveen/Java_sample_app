//import system.pullRequest.sourceBranch
//import system.pullRequest.targetBranch
node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		def JobName = "${JOB_NAME}"
		def index = JobName.indexOf("/");
		def SonarHostName = JobName.substring(0 , index)+"_"+"${BRANCH_NAME}"
		///Println "${PULL_REQUEST}"
		echo sh(returnStdout: true, script: 'git branch --contains')
		println ${SYSTEM_PULLREQUEST_SOURCEBRANCH}
		def LockVar = SonarHostName
		if(JobName.contains('PR-'))
		{
			SonarHostName = SonarHostName+"_"+"PR"
		}
		println SonarHostName
		println JobName
		/*if(!temp.contains('PR-'))
		{
			temp2 = temp.replaceAll('/','-')
			println temp2
		 }
		else
		{
			
		temp2 = temp.replace('/','-')
		 def iend = temp2.indexOf("-");
		 temp2 = temp2.substring(0 , iend)+"-"+"${BRANCH_NAME}"+"-"+"PR";
		  println temp2;
		}*/
		
		
		sh '''var=${BRANCH_NAME} docker-compose up -d
			'''
	}
    }
