pipeline {
    agent { label 'DOCKER-TASK-2'}
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('testing-docker') {
            steps {
                sh 'docker info'
                sh 'docker image build -t spring-pet-clinic'
                sh 'docker image ls'
                sh 'docker conatiner run --name spc -it -d -P spring-pet-clinic'
                sh 'docker container ls'
            }
        } 
    }
}
