pipeline {
    agent any
    
    stages {

        stage ('build the docker image') {
            steps {
                sh 'docker build -t yannmanux/furniture'
            }
        }
    }
}