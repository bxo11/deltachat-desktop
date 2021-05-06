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
            
            stage('Test') {
            steps {
                sh '''
                echo 'Testing..'
                docker build -f Dockerfile-test-agent .
                '''
                }
        }
         
        }
        
        failure {
            echo 'Build failed!'
           
        }
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
