// SCRIPTED
// node {
// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"
// }

//DECLARATIVE
pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'node:13.8' } }
	stages {
		stage('build'){
			steps {
				// sh "mvn --version"
				// sh "node --version"
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
		stage('Test'){
			steps {
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps {
 				echo "Integration Test"
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
