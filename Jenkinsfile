pipeline {
    agent any
    
    stages {
        stage('Use Credentials') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'checksamepattern', 
                                                 usernameVariable: 'USERNAME', 
                                                 passwordVariable: 'PASSWORD')]) {
                    sh '''
                        echo "Using Jenkins Credentials"
                        echo "Username: $USERNAME"
                        # Don't print the password directly for security reasons
                        echo "Making a curl request with credentials..."
                        curl -u $USERNAME:$PASSWORD https://httpbin.org/basic-auth/$USERNAME/$PASSWORD
                    '''
                }
            }
        }
    }
}
