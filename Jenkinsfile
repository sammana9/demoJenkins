pipeline{
  agent any
  tools{
   maven 'Maven'
  
  }
  
environment {

CREDENTIAL_SERVER = credentials('credential-server')
}

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
		   sh 'mv test'
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
	   echo "printing credentials ${CREDENTIAL_SERVER}"
	   sh ''' echo "creds:${CREDENTIAL_SERVER}" '''
	  }
  }
}
}
