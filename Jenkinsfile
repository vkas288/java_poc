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

		stage('Hello-World') {
			steps {
				echo 'hello world'
			}
		}
	}
}			
