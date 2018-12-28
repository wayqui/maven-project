pipeline {
    agent any

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
    }
}