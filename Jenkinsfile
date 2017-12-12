node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		def temp = "h/i"
		def temp2 = temp.replaceAll('/','-')
		println temp2
		sh '''var=${BRANCH_NAME} docker-compose up -d
			'''
	}
    }
