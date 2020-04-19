pipeline {
        agent {
  label 'Jenkins Slave'
}
	
	
    stages {
	
		stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/sbasurya/docker-sample-website.git"
            }
			}
        stage('Build') { 
            steps {
                echo "hello Build Stage"
				sh "docker build -t jenkins-docker ."
            }
        }
        stage('Tag') { 
            steps {
                echo "hello Tag Stage"
				sh "docker tag jenkins-docker sbasurya/jenkins-image"
				
            }
        }
        stage('Login') { 
            steps {
                echo "Hello Login Stage"
				sh "docker login --username=sbasurya --password=Mohanprudhvi30"
            }
        }
		stage('Push') { 
            steps {
                echo "Hello Pushing Image to DockerHub"
				sh "docker push sbasurya/jenkins-image"
            }
        }
    }
}
