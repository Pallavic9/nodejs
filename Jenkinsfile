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
        
    }
}
