node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/Mohnishg19/codeforsnykrepo.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '89d63504-e7e2-42be-943a-689f6f7eac57', snykInstallation: 'Snyk1', snykTokenId: 'Snykkey'
       
   }

}
