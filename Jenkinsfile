pipeline {
    agent any

    stages {
        stage('Pre') {
            steps {
                sh '''
                curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
                chmod +x /usr/local/bin/docker-compose
                docker --version
                docker-compose --version
                ls
                '''
                }
        }
        stage('Test') {
            steps {
                sh '''
                echo 'Testing..'
                docker-compose up
                '''
                }
        }
       
    }
    
    post {
        
        success {
            echo 'Success!'
        }
        
        failure {
            echo 'Failure!'
        }
    }
}
