pipeline{
  agent any

stages {
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
            echo 'hello this new compile'
          }
          }
      stage('test') {
	  when {
	  expression {
	   env.BRANCH_NAME =='dev'
	  }
	  }
        steps {
          echo 'hello this new test'
        }
      }
	  stage('creds'){
	  steps{
	 
	   withCredentials([usernamePassword(credentialsId:'credential-server',usernameVariable:'USER',passwordVariable:'PWD')]){
	   
	   
	  sh ''' "echo Username:${USER}" '''
	  
	   }
	  }
  }
}
}
