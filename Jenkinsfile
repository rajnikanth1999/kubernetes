pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('deployment') {
            steps {
                sh '''
                kubectl apply -f db-service.yml
                kubectl apply -f cache.yml
                kubectl apply -f saleor.yml
                kubectl apply -f test.yml
                '''
            }
        }
    }
}