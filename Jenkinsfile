pipeline {
    // master executor should be set to 0
    agent any
    stages {
        stage("Start Grid") {
            steps {
                //sh
                bat "docker-compose up -d hub chrome firefox"
            }
        }
	stage("Run Test") {
	    steps {
                bat "docker-compose up book-flight-module2"
            }
        }
    }  
    post{
        always{
                archiveArtifacts artifacts: 'C:/Users/DockerHost/TestResults'
            	bat "docker-compose down"
	}
    }        
}