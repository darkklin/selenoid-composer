pipeline{
	agent any
	stages{
		stage("Pull latest Image"){
			steps{
				sh "docker pull darkklin/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d"
			}
		}
		stage("Run The Test"){
			steps{
				sh "docker-compose up search-module book-flight-module"
		   }
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		
		}
	}
	
}