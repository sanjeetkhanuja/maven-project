pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
				sh 'mvn clean package'
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