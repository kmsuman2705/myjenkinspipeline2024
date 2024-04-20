pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                echo "git pull my code step1"
                git 'https://github.com/kmsuman2705/myjenkinspipeline2024.git'
            }
        }

        stage('Deploy') {
            steps {
                echo "deploying my code"
            }
        }

        stage('Test') {
            steps {
                echo "test my final webapp"
            }
        }
        
        stage('Deploy to Prod') {
            steps {
                echo "my final webapp to prod"
            }
        }
    }
}
