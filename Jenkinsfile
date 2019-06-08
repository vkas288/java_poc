pipeline {

	options {
		buildDiscarder(logRotator(daysToKeepStr: '15'))
		disableConcurrentBuilds()
	}

	triggers {
		cron('@daily')
	}

	agent {
		label 'Jenkins-Node1'
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
		stage('package') {
			steps {
				sh "mvn package"
				jacoco( 
				      execPattern: 'target/*.exec',
				      classPattern: 'target/classes',
				      sourcePattern: 'src/main/java',
				      exclusionPattern: 'src/test*'
				)
			}
		}
		stage('verify') {
			steps {
				sh "mvn verify"
			}
		}
		stage('install') {
			steps {
				sh "mvn install"
			}
		}
		stage('deploy') {
			steps {
				sh "echo 'skipping mvn deploy'"
			}
		}
	}
}			
