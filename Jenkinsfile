pipeline {
	agent any
	//agent {docker {image 'maven:3.6.3'}}
	environment {
		dockerHome = tool "myDocker"
		mavenHome = tool "myMaven"
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout') {
			steps {
				sh "mvn --version"
				sh "docker --version"
				echo "Build"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
	    }
		stage('Test') {
			steps {
				echo "Test"
			}
	    }
		stage('Compile'){
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				echo "mvn Test"
			}
	    }
		stage('Integration Test') {
			steps {
				echo "mvn failsafe:integration-test failsafe:verify"
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
