
pipeline {
	agent any
    stages {
	stage('Checkout') {
            steps {
				checkout([
                    $class: 'GitSCM', 
                    branches: master,
                    userRemoteConfigs: [
                        [
                            name: 'nodejs',
                            credentialsId: 'jenkins',
                            url: 'git@github.com:Pallavic9/nodejs.git'
                        ]
                    ]
                ])
            }
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
