
pipeline {
	node any
    stages {
	    stage("Checkout") {
		git credentialsId: 'docker-cred', url: 'https://github.com/Pallavic9/nodejs.git'	    
	    }
        
        stage("Build Nodejs Docker image ") {
            steps {
                dir('.') {
                    sh (
                        label: 'Node js docker image build',
                        script: 'docker build -t web-app . && docker tag web-app:latest pallavic9/my-images:node'
                    )
                }
            }
        }      
        
    }
}
