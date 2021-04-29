pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh """
                echo 'Testing..'
                curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
                chmod +x /usr/local/bin/docker-compose
                docker --version
                docker-compose --version
                pwd
                """
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
