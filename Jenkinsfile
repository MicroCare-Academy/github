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

  }
  
   
}
