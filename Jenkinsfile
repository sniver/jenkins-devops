pipeline {
	//agent { docker{ image 'maven:3.8-jdk-8'}}
	agent any
	environment{
		dockerHome = tool 'MyDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout') {
			steps{
				sh 'mvn --version'
				//sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD NUMBER - $env.BUILD_NUMBER"
				echo "BUILD ID - $env.BUILD_ID"
				echo "JOB NAME - $env.JOB_NAME"
				echo "BUILD TAG - $env.TAG"
				echo "BUILD URL - $env.BUILD_URL"
			}
		}
		
		stage('Compile'){
			sh "mvn clean compile"
		}
		
		stage('Test') {
			steps{
				sh "mvn test"
			}
		}
		
		stage('Integration Test') {
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	}
}
