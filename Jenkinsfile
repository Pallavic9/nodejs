import groovy.transform.Field
pipeline {
	agent any
    stages {
	stage("Checkout") {
            steps {
			git branch: 'master',
			credentialsId: 'jenkins',
			url: 'https://github.com/Pallavic9/nodejs.git'
            }
        }

        stage("Build Nodejs Docker image ") {
            steps {
		    sh (
                        label: 'Node js docker image build',
                        script: 'docker build -t web-app . && docker tag web-app:latest pallavic9/my-images:node'
                    )
                
            }
        }      
	    stage("Push docker image to docker hub") {
		    step {
		   sh (
		 	label: 'push docker image to docker hub'
			script: 'docker push pallavic9/my-images:node'
		      )
		    }
		    stage("run image") {
			    step{
				    sh(
					    script: 'docker run -itd -p 49160:8080 pallavic9/my-images:node'
					    )
			    }
		    }
    }
}
