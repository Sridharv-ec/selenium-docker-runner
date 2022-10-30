pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
				echo "executed docker-compose command for chrome and firefox browser"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up book-flight-module"
				echo "executed docker-compose for running search-module and book-flight-module"
			}
		}
	}
	post{
		always{
			sh "docker-compose down"
		}
	}
}