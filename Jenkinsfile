pipeline {

	options {
		buildDiscarder(logRotator(daysToKeepStr: '15'))
		disableConcurrentBuilds()
	}

	triggers {
		cron('@daily')
	}

	agent {
		label 'Jenkins-Master'
	}

	stages {

		stage('validate') {
			steps {
				sh "mvn validate"
			}
		}
		stage('compile') {
			steps {
				sh "mvn compile"
			}
		}
		stage('test') {
			steps {
				sh "mvn test"
			}
		}
		stage('validate') {
			steps {
				sh "mvn package"
			}
		}
		stage('validate') {
			steps {
				sh "mvn install"
			}
		}
		stage('validate') {
			steps {
				sh "mvn deploy"
			}
		}
	}
}			
