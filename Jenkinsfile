//import system.pullRequest.sourceBranch
//import system.pullRequest.targetBranch
node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		def JobName = "${JOB_NAME}"
		def index = JobName.indexOf("/");
		def SonarHostName = JobName.substring(0 , index)+"_"+"${BRANCH_NAME}"
		//Println "${PULL_REQUEST}"
		echo sh(returnStdout: true, script: 'git shortlog -s -n')
		println "${env.ghprbSourceBranch}"
		def content = readFile './.env'
  			Properties properties = new Properties()
  			InputStream contents = new ByteArrayInputStream(content.getBytes());
  			properties.load(contents)
  			contents = null
			def branch_name = properties.branch_name
			println "${branch_name}"
		/* sh '''
    			git rev-parse --abbrev-ref HEAD > GIT_BRANCH'
    			git_branch = readFile("GIT_BRANCH").trim()
    			echo git_branch
   		  ''' */
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

