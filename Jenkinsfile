pipeline {
    agent any
   
        stage('clone') {
    git 'https://github.com/SnehaKailasa/Java_sample_app.git'
    }
    stage('build'){
        sh 'mvn -f SpringMVCSecurityXML/pom.xml clean install '
        }
    
}
