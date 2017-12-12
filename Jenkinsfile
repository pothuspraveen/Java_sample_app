node{
	stage ('git'){checkout scm}
   	stage ('Build') {
		def temp = "h/PR-"
		def iend = temp.indexOf("/");
		def temp2 = temp.substring(0 , iend)+"_"+"${BRANCH_NAME}"
		if(temp.contains('PR-'))
		{
			temp2 = temp2+"_"+"PR"
		}
		println temp2
		/*if(!temp.contains('PR-'))
		{
			temp2 = temp.replaceAll('/','-')
			println temp2
		 }
		else
		{
			
		temp2 = temp.replace('/','-')
		 def iend = temp2.indexOf("-");
		 temp2 = temp2.substring(0 , iend)+"-"+"${BRANCH_NAME}"+"-"+"PR";
		  println temp2;
		}*/
		
		sh '''var=${BRANCH_NAME} docker-compose up -d
			'''
	}
    }
