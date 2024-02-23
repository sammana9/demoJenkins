
def gv
pipeline{
  agent any
options{
  buildDiscarder(logRotator(numToKeepStr:'15'))
 }
  tools{
   maven 'Maven'
  
  }

  parameters {
  
  string(name:'FirstName', defaultValue:'SureshAmmana', description:'testing')
  }
  
environment {

CREDENTIAL_SERVER = credentials('credential-server')
}

  stages {
  
stage('userfetch'){
steps{
wrap([$class:'BuildUser']){

 script{
 def usrname="${BUILD_USER}"
 if(usrname=='suresh')
 {
 error " build aborted"
 }
 else{
 
 echo 'no one can build this except suresh'
 }
 }
}

}
}

  
  stage('approvalrequest')
  {
  steps{
   input('suresh please approve this build')
	script {
		sh "echo this is approved"
	}
  }
  }
  
  
  stage('debug'){
  steps{
  
  echo "BRANCH_NAME:${BRANCH_NAME}"
  
  }
  }
  
    stage('compile') {
	when {
	expression {
	  env.BRANCH_NAME=='main'
	}
	}
          steps {
		   sh 'mvn test'
            echo 'hello this new compile'
			
          }
          }
      stage('test') {
	  when {
	  expression {
	   env.BRANCH_NAME =='dev' || env.BRANCH_NAME=='main'
	  }
	  }
        steps {
          echo "hello this new test ${params.FirstName}"
		
        }
      }
	  stage('creds'){
	  steps{
	   echo "printing credentials ${CREDENTIAL_SERVER}"
	   sh ''' echo "creds:${CREDENTIAL_SERVER}" '''
	  }
  }
  
  stage('groovy') {
  
  steps{
  
   script{
     gv= load 'demo.groovy'
	  
	  echo " test ${gv}"
   }
  }
  }
  stage('checkout'){
  
  steps{
  
  git branch: 'main',url:'https://github.com/sammana9/demoJenkins.git'
   script{
   def gitcommit =env.GIT_COMMIT
   echo "newcommitnumber: ${gitcommit}"
   }
   
   
   
  }
  
  post {
  success{
  archiveArtifacts 'target/**'
  }
  }
  
  }
  
  
}
}
