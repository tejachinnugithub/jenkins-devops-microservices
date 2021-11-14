pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'

		PATH = "$mavenHome/bin:$dockerHome/bin:$PATH" 
	}
	stages {
		stage('Build'){
			steps {
				sh 'mvn --version'
				sh 'docker --version'
				echo "Build" 
			}
		}
	}
}
