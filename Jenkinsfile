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
                '''
                }
        }
       
    }
    
    post {
        
        success {
            echo 'Success!'
            emailext body: 'Test Message',
            subject: 'Success tests',
            to: 'krzysiek.klim1999@gmail.com'
            
            mail to: 'krzysiek.klim1999@gmail.com',
            subject: "Status of pipeline: ${currentBuild.fullDisplayName}",
            body: "${env.BUILD_URL} has result ${currentBuild.result}"
         
        }
        
        failure {
            echo 'Failure!'
            emailext body: 'Test Message',
            subject: 'Tests failed',
            to: 'krzysiek.klim1999@gmail.com'
        }
         }
   
}
