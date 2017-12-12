node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		sh ''' export var = ${BRANCH_NAME}
			docker-compose up -d
			'''
	}
    }
