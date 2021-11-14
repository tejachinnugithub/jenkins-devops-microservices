pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'

		PATH = "$mavenHome/bin:$dockerHome/bin:$PATH" 
	}
	stages {
		stage('Checkout'){
			steps {
				sh 'mvn --version'
				sh 'docker --version'
				echo "Build" 
			}
		}
		stage('Compile'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
			}
			
		}
		stage('Integration Test'){
			steps{
				sh 'mvn failsafe:integration-test failsafe:verify'
			}
		}
	}
}
