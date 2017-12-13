//import system.pullRequest.sourceBranch
//import system.pullRequest.targetBranch
node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		def JobName = "${JOB_NAME}"
		def SonarHostName
		//Println "${PULL_REQUEST}"
		//echo sh(returnStdout: true, script: 'git shortlog -s -n')
		//println "${env.ghprbSourceBranch}"
		def content = readFile './.env'
  			Properties properties = new Properties()
  			InputStream contents = new ByteArrayInputStream(content.getBytes());
  			properties.load(contents)
  			contents = null
			def branch_name1 = properties.branch_name
			println "${branch_name1}"
		/* sh '''
    			git rev-parse --abbrev-ref HEAD > GIT_BRANCH'
    			git_branch = readFile("GIT_BRANCH").trim()
    			echo git_branch
   		  ''' */
		def LockVar = SonarHostName
		if(JobName.contains('PR-'))
		{
			def index = JobName.indexOf("/");
			SonarHostName = JobName.substring(0 , index)+"_"+"${branch_name1}"
			
		}
		else
		{
			def index = JobName.indexOf("/");
			SonarHostName = JobName.substring(0 , index)+"_"+"${BRANCH_NAME}"
		}
		println SonarHostName
		println JobName
		sh '''var=${BRANCH_NAME} docker-compose up -d
			'''
	}
    }

