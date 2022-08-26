pipeline{
	agent any
	
	stages{
		stage("DOCKER BUILD"){
			steps{
				echo "BUILD stage"
				sh ''' 
					cd /var/lib/jenkins/workspace/build
					docker build -t priyappatil/jenkins:1.10 .
				'''
			}
		}
		stage("DOCKER PUSH"){
	                 steps{
				sh 'docker image ls'
				sh 'docker push priyappatil/jenkins:1.10'
				echo "Docker image pushed to docker hub successfuly"
			}
		}
		
		stage("Docker-run"){
			steps{
				echo "Running container"
				sh 'docker run -it -d -p 8060:8080 --name priyatomcat priyappatil/jenkins:1.10'
				
			}
		}
	}
}
