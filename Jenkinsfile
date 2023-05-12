pipeline { 

    agent any

    environment {
        DOCKERHUB_CREDENTIALS= credentials('manudocker')
    }
    
    stages {

        stage ('build the docker image') {
            steps {
                sh 'docker build -t yannmanux/furniture2 .'
            }
        }

        stage ('login to dockerhub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW |  docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                   echo 'login completed'
            }
        }
    
        stage ('push the image into dockerhub') {
            steps {
                sh ' docker push yannmanux/furniture'
            }
        }
    } 

    post {

        always {
            sh 'docker logout'
        }
    } 

}

