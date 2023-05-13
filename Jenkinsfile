pipeline { 

    agent any

    environment {
        DOCKERHUB_CREDENTIALS= credentials('Dockerhub')
    }
    
    stages {

       stage ('build the docker image') {
            steps {
                sh 'docker ps'
            }
        }  
    } 

}

