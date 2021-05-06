pipeline {
    agent any

    stages {
        stage('Pre') {
            steps {
                sh '''
                ls
                '''
                }
        }
        
        stage('Build') {
            steps {
                sh '''
                echo 'Building..'
                docker build -f Dockerfile-build-agent .
                '''
                }
                
                post {
        
        success {
            echo 'Build success!'
            
         
        }
        
        failure {
            echo 'Build failed!'
           
        }
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
            
         
        }
        
        failure {
            echo 'Failure!'
           
        }
         }
   
}
