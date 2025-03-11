pipeline {
    agent any


    triggers {
        pollSCM('H/30 * * * *')
    }




    stages {
        stage('Checkout') {
            steps {

                git branch: 'main', url: 'https://github.com/NirFakiro/My-App-backend.git'
            }
        }

        stage('Run backend_testing') {
            steps {
                echo 'Running backend app...'
                sh 'python testing/backend_testing.py'
            }
        }

        stage('Run frontend_testing') {
            steps {
                echo 'Running frontend app...'
                sh 'python testing/frontend_testing.py'
            }
        }

        stage('Clean environment') {
            steps {
                echo 'Cleaning environment...'
                sh 'python clean_environment.py'
            }
        }
    }
}
