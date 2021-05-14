
#!/usr/bin/env groovy

pipeline {


    agent {
		
    }


    stages {
        
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
