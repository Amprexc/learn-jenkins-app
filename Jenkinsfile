pipeline {
    agent any

    stages {
        stage('Build ') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci 
                    npm run build
                    ls -la
                '''
            }
        }
    }
    
    post{
        success{
            echo 'Success'
        }
        failure{
            echo 'Failed'
        }
        
    }
}
