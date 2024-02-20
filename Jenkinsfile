pipeline{
  agent any
  environment {
  CODE_CHANGES = true
  }
  stages {
    stage('compile') {
	when {
	expression {
	  BRANCH_NAME=='main' && echo "code changes ${CODE_CHANGES}"
	}
	}
          steps {
            echo 'hello this new compile'
          }
          }
      stage('test') {
	  when {
	  expression {
	   BRANCH_NAME =='dev'
	  }
	  }
        steps {
          echo 'hello this new test'
        }
      }
  }
}
