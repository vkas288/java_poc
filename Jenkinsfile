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

		stage('maven') {
			steps {
				echo 'pre validate'
				sh "id -u jenkins"
				sh "id 1005"
				echo 'post validate'
			}
		}
	}
}			
