pipeline {
	//agent { docker{ image 'maven:3.8-jdk-8'}}
	agent any
	environment{
		dockerHome = tool 'MyDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build') {
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
		
		stage('Test') {
			steps{
				echo "Test"
			}
		}
		
		stage('Integration Test') {
			steps{
				echo "Integration Test"
			}
		}
	}
}
