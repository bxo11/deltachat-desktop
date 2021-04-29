pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Testing..'
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
