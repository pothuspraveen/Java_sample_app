node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		sh 'echo ${JOB_NAME}'
		sh 'mvn -f SpringMVCSecurityXML/pom.xml clean install '
	}
    }
