pipeline {
    agent any
    try {
	    stages {
	        stage('Build') {
	            steps {
	                sh 'echo "Hello world!"'
	            }
	        }
	    }	
    }
    catch(any) {
    	currentBuild.result = 'FAILURE'
    	throw any // rethrow exception
    }
    finally {
    	def colorCode = '#00ff00'
	    def buildStatus = 'SUCCEEDED'
	    switch (currentBuild.result) {
	      case 'ABORTED':
	        colorCode = '#888888'
	        buildStatus = 'ABORTED'
	        break
	      case 'FAILURE':
	        colorCode = '#FF0000'
	        buildStatus = 'FAILED'
	        break
	    	}		
	    }
}
