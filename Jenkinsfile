CODE_CHANGES = getGitChanges()
pipeline{
  agent any
  stages {
    stage('compile') {
	when {
	expression {
	  BRANCH_NAME=='main' && CODE_CHANGES==true
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
