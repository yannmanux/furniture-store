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
                sh 'echo dckr_pat_upOl8ZRFZZQ82HJH--eK-8AyI0Y |  docker login -u $DOCKERHUB_CREDENTIALS_USR -- password-stdin'
                   
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

