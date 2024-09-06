pipeline {
    agent any
    
    environment{
        BUILD_FILE_NAME = 'laptop.txt'
    }

    stages {
        stage('Build ') {
            steps {
                cleanWs()
                echo "$BUILD_FILE_NAME"
                sh '''
                    mkdir -p build
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
