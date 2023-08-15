pipeline {
    agent any

    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('demo')
    }
    
    stages {
        stage('build') {

            when {

                expression {
                    BRANCH_NAME == 'master'
                }
            }
            steps {
                echo 'Building the project...'
                echo "Building project of version ${NEW_VERSION}"
            }
        }

        stage('test') {
            steps {
                echo 'testing the project...'
            }
        }

        stage('deploy') {
            steps {

                echo 'Deploying the project...'
                withCredentials([
                usernamePassword(credentials: 'demo', usernameVariable: 'USER', passwordVariable: 'PWD')
            ]) 
             
            {
                echo "Injected username as ${USER} and password as ${PWD}"
            // You can use the injected credentials here for deployment
            }
        }
    }

}
