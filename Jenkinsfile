pipeline {
    agent any

    tools {
        maven 'localMaven'
    }

    stages {
        stage('Build') {
            steps {
				sh 'mvn clean package'
			}
			post {
				success {
					echo 'Ahora generando WAR'
					archiveArtifacts artifacts: '**/target/*.war'
				}
			}
        }
		stage('Deploy to Stagging') {
			steps {
				build job: 'Lesson5-Deploy-to-Stagging'
			}
		}
    }
}