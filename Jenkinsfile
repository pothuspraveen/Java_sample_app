node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		def temp = "h/i"
		def temp2 = temp.replaceAll('/','-')
		sh '''var=${BRANCH_NAME} docker-compose up -d
			'''
	}
    }
