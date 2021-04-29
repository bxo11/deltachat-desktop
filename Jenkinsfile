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
            notifySuccessful()
        }
        
        failure {
            echo 'Failure!'
        }
         }
    
def notifySuccessful() {
             smail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "kklimczyk@student.agh.edu.pl";
         }
}
