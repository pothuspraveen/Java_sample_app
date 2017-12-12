node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		sh '''var=${BRANCH_NAME} docker-compose up -d
			'''
	}
    }
