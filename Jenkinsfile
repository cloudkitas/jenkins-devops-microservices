// SCRIPTED
// node {
// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"
// }

//DECLARATIVE
pipeline {
	agent any
	environment {
		dockerHome = tool 'MyDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'node:13.8' } }
	stages {
		stage('Checkout'){
			steps {
				 sh "mvn --version"
				 sh "docker --version"
				//test
				echo "Build"
				echo "$PATH"
				echo "Build Numer - $env.BUILD_NUMBER"
				echo "Build ID - $env.BUILD_ID"
				echo "JOB Name - $env.JOB_NAME"
				echo "Build TAG - $env.BUILD_TAG"
				echo "Build URL - $env.BUILD_URL"
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Test'){
			steps {
 				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	} 
	
	post {
		always {
			echo 'Im awesome. I run always'
		}
		success {
			echo 'I run when you are successful'
		}
		failure {
			echo 'I run when you fail'
		}
	}
}
