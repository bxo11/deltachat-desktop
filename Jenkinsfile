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
                
                '''
                }
                
                post {
        
        success {
            echo 'Build success!'
            
            stage('Test') {
            steps {
                sh '''
                echo 'Testing..'
                
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
