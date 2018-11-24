pipeline {
         agent any
         stages {
                 stage('One step') {
                 steps {
                     echo 'Hi, this is Zulaikha from edureka'
                 }
                 }
                 stage('Two Step') {
                 steps {
                    input('Do you want to proceed?')
                 }
                 }
                 stage('Three Step') {
                 when {
                       not {
                            branch "master"
                       }
                 }
                 steps {
                       echo "Hello"
                 }
                 }
                 stage('Four') {
                 parallel { 
                           stage('UniT Test') {
	                           steps {
        	                        echo "Running the unit test..."
                	           }
                           }
                           stage('Integration test') {
                         	  agent {
                                    docker {
                                            reuseNode true
                                            image 'ubuntu'
                                           }
                                    }
                             		 steps {
                                		echo "Running the integration test..."
                              			}
                           }
                           }
                           }
              }
}
