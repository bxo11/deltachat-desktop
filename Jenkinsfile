pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                echo 'Building..'
                docker build -f Dockerfile-build-agent .
               
                '''
            }
                
        
            post {
                success {
                    echo 'Success!'
                    emailext attachLog: true,
                    body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}",
                    recipientProviders: [developers(), requestor()],
                    subject: "Success Jenkins Build",
                    to: 'krzysiek.klim1999@gmail.com'
                }
            
                failure {
                    echo 'Failure!'
                    emailext attachLog: true,
                    body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}",
                    recipientProviders: [developers(), requestor()],
                    subject: "Failed Jenkins Build",
                    to: 'krzysiek.klim1999@gmail.com'
                }
            }
        }
         
        stage('Test') {
            steps {
                sh '''
                echo 'Testing..'
                docker build -f Dockerfile-test-agent .
                '''
                }

            post {
                success {
                    echo 'Success!'
                    emailext attachLog: true,
                    body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}",
                    recipientProviders: [developers(), requestor()],
                    subject: "Success Jenkins Test ${currentBuild.currentResult}: Job ${env.JOB_NAME}",
                    to: 'krzysiek.klim1999@gmail.com'
                }
        
                failure {
                    echo 'Failure!'
                    emailext attachLog: true,
                    body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}",
                    recipientProviders: [developers(), requestor()],
                    subject: "Failed Jenkins Test ${currentBuild.currentResult}: Job ${env.JOB_NAME}",
                    to: 'krzysiek.klim1999@gmail.com'
                }
            }
        }
    }
}
