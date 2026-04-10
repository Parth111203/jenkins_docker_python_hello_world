//Jenkinsfile
pipeline {
	agent any
	
	environment {
		DOCKER_IMAGE = 'hello-world-python:latest' //Docker
		image name
	}

	stages {
		stage('checkout') {
		steps {
			git branch: 'main', url:
			'https://github.com/Parth111203/jenkins_docker_python_hello_world.git'
			}
		}

		stage('Docker Build') {
			steps {
				script {
				
					if (fileExists ('Dockerfile')) {
					sh "docker build -t
					${env.DOCKER_IMAGE} ."
					} else {
						error "Dockerfile not found in the workspace. Please create one for your python application."
						}
					}
				}
			}
			
			stage('Docker Run (optional)') {
				steps {
					sh "docker run --rm ${env.DOCKER_IMAGE}"
							}	     
					}
			}

	post {
		success { echo 'Success' }
		failure { echo 'Failure' }   
		} 
	}
