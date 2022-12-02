pipeline {
    agent { label 'DOCKER'}
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('testing-docker') {
            steps {
                sh 'pwd'
                sh 'docker build -t new .'
                sh 'docker run -d --name spc1 -p 8081:8080 new'
                sh 'curl http://localhost:8081' 
                
                  
            }
        }
       
    }
}
