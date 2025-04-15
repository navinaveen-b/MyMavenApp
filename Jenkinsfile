pipeline {
	agent any //use any available agent
	tools {
		maven "Maven"
	}
	stages {
		stage('Checkout') {
			steps {
		git branch: 'master', url: 'https://github.com/navinaveen-b/MyMavenApp.git'
			}
		}
		stage('Build') {
			steps {
				sh 'mvn clean install' //run maven build
			}
		}
		stage('Test') {
			steps {
				sh 'mvn test' //Run unit tests
			}
		}
		stage('Run Application') {
			steps {
				sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
			}
		}
	}
	post {
		success {
			echo 'Build and deployment sucessful'
		}
		failure {
			echo 'Build failed'
		}
	}
}
			
