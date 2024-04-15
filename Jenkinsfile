pipeline {
	agent {
		docker{
			image 'maven:3.8-jdk-8'
		}
	}
	stages{
		stage('Build') {
			steps{
				sh 'mvn --version'
				sh 'java -version'
				echo "Build"
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
