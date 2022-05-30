pipeline {

   agent any
	  environment {

    PATH_DIR = "/home/"
  }
	options {
		 buildDiscarder(logRotator(numToKeepStr:'5'))
		timestamps()
	 timeout(time: 10, unit: 'MINUTES')}
   stages{

   		stage('Checkout') { // for display purposes
    		steps {
			
      			// this will checkout the branch/master based on the commit file
			sh 'echo "THIS IS BUILD NUMBER $BUILD_NUMBER"'
			sleep(10)
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
	    stage('PATH') {
    		steps {
      			// Run the maven build check extra
			sh 'pwd'
      			sh 'cd $PATH_DIR'
			sh 'pwd'
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
