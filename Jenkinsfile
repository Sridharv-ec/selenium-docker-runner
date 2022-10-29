pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				sh "docker pull sridharvuttarkar/selenium-docker"
				echo "pulled docker image selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
				echo "executed docker-compose command for chrome and firefox browser"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up search-module1 book-flight-module1"
				echo "executed docker-compose for running search-module and book-flight-module"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
			sh "sudo rm -rf output/"
		}
	}
}