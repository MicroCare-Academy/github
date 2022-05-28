pipeline {

   agent any
   stages{

   		stage('Checkout') { // for display purposes
    		steps {
      			// this will checkout the branch/master based on the commit file
       			checkout scm
    		}
  		}
  		
stage('Build') {
    		steps {
      			// Run the maven build check extra
      			sh 'mvn clean compile'
    		}
  		}
	   stage('Test') {
    		steps {
      			// Run the maven build check extra
      			sh 'mvn test'
    		}
  		}

  }
  post { 
        success { 
            echo 'SUCCESSFUL'
        }
		 failure { 
            echo 'FAILURE'
        }
		aborted{
			echo 'ABORTED BY ME MANUALLY'
		}
    }
  
   
}
