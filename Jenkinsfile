//import system.pullRequest.sourceBranch
//import system.pullRequest.targetBranch
node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		def JobName = "${JOB_NAME}"
		def index = JobName.indexOf("/");
		def SonarHostName = JobName.substring(0 , index)+"_"+"${BRANCH_NAME}"
		//Println "${PULL_REQUEST}"
		echo sh(returnStdout: true, script: 'git branch --contains')
		println "{env.GIT_BRANCH}"
		def LockVar = SonarHostName
		if(JobName.contains('PR-'))
		{
			SonarHostName = SonarHostName+"_"+"PR"
		}
		println SonarHostName
		println JobName
		sh '''var=${BRANCH_NAME} docker-compose up -d
			'''
	}
    }
