pipeline {
    agent any

    stages {
        stage('Build') {
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
        stage('Test'){
            steps {
                sh '''
                    echo 'Test stage'
                    if ! [ -f /build/index.html ]; then
                        echo "File index does not exist."
                    fi

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
