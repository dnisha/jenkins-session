pipeline {

    agent any
   
    parameters {
        string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod')
        choice(name: 'ENVIRONMENT', choices: ['dev', 'staging', 'production'], description: 'Select deployment environment')
        booleanParam(name: 'CLEAN_BUILD', defaultValue: true, description: 'Perform a clean build')
    }

    tools {
        maven 'MAVEN'
    }

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
            }
        }
    }
}
