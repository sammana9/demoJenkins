
def gv
pipeline{
  agent any
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
      gv.hellworld()
	  
	  echo " test ${gv}"
   }
  }
  }
  
}
}
