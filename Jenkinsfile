pipeline {
	//agent any
	//agent {docker {image 'maven:3.6.3'}}
	stages{
		stage('Build') {
			steps {
				//sh "mvn --version"
				echo "Build"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
			}
	    }
		stage('Test') {
			steps {
				echo "Test"
			}
	    }
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
	    }
	} 
	post{
		always {
			echo "I am awsome. I run always"
		}
		success {
			echo "I run when you are a successful"
		}
		failure {
			echo "I run when you fail"
		}
	}

	
}
