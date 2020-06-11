
 pipeline {
    agent any
       
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/kaza514/docker_push.git'
            }
        }   
    
        stage('Build image') {
            app = docker.build("kaza514/test")
            }   


        stage('Push image') {

            docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
                app.push("${env.BUILD_NUMBER}")
                app.push("latest")
                } 
                echo "Trying to Push Docker Build to DockerHub"
        }
    
    }

 }