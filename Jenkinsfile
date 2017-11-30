node{


	stage ('git'){checkout scm}
    stage('clone')
    {
         git 'https://github.com/SnehaKailasa/Java_sample_app.git'
    }
	stage ('Build') {
		sh 'mvn -f SpringMVCSecurityXML/pom.xml clean install '
	}
}
