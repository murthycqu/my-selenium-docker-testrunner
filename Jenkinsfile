pipeline {
    // master executor should be set to 0
    agent any
    stages {
		stage('Grid UP') {
            steps {
                //sh
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage('Run Test') {
            steps {
                //sh
                bat "docker-compose up search-module book-flight-module"
            }
        }
    }
	post {
		always{
			bat "docker-compose down"
			//archiveArtifacts artifacts: '//target/*.*'
		}
	}
}