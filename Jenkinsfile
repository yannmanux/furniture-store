pipeline { 

    agent any

    environment {
        DOCKERHUB_CREDENTIALS= credentials('Dockerhub')
    }
    
    stages {

       stage ('build the docker image') {
            steps {
                sh 'docker build -t yannmanux/furniture2 .'
            }
        }  
        stage ('login to dockerhub') {
        steps {
                sh 'docker login --username yannmanux --password dckr_pat_Kt9bOTZL6zG9Ge-3WJLoVoTHcfw'
                   
            }
        }
    
        stage ('push the image into dockerhub') {
            steps {
                sh ' docker push yannmanux/furniture2'
            }
        }
    } 

    post {

        always {
            sh 'docker logout'
        }
    } 
}

