pipeline {
	// agent any
	agent { docker { image 'maven:3.6.3'} }
	stages {
		stage('Build'){
			steps {
				sh 'maven --version'
				echo "Build" 
			}
		}
	}
}
