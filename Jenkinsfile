#!/usr/bin/env groovy​

pipeline {


    agent {
		
    }


    stages {
        
        stage("Build Nodejs ") {
            steps {
                dir('.') {
                    sh (
                        label: 'Mvn',
                        script: 'mvn -DskipTests clean package'
                    )
                }
            }
        }      
        
    }
}
