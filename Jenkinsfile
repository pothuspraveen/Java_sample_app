node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		sh 'mvn -f SpringMVCSecurityXML/pom.xml clean install '
	}
    }
