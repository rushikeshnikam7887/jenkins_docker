//jenkinsfile
pipeline {
	agent any
	environment {
		DOCKER_IMAGE = 'hello-world-python:latest'
	}

	stages {
		stage ('Checkout') {
			step {
				git branch: 'main', url:'https://github.com/rushikeshnikam7887/jenkins_docker.git'
			}
		}

		stage('Docker Build') {
			steps {
				if (fileExists('Dockerfile')) {
					sh "Docker build -t ${env.DOCKER_IMAGE} ."
					} else {
						error "Dockerfile not found in the workplace."
					}
				}
			}
		}

		stage('Docker Run (Optional)') {
			steps {
				sh "Docker run --rm ${env.DOCKER_IMAGE}"
			}
		}
	}

	post {
		success {
			echo 'success'
		}
		failure {
			echo 'failure'
		}
	}

  

















