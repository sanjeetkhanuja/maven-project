pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
				mvn clean
            }
			post {
				success {
					echo 'Archiving'
					archiveArtifacts artifacts: '**/target/*.war'
				}	
			}
        }
    }
}