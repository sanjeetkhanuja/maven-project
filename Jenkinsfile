pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
				bat 'mvn clean package'
            }
			post {
				success {
					echo 'Archiving'
					archiveArtifacts artifacts: '**/target/*.war'
				}	
			}
        }
		stage('Deploy to DEV env') {
			steps {
				build job: 'deploy_to_DEV_env'
			}
		}		
    }
}