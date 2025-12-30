pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
               git branch: 'main',
                   url: 'https://github.com/bijuthomaspta/New_Node_JS_App.git'
# git 'https://github.com/bijuthomaspta/New_Node_JS_App.git'
                
                
                
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop app || true
                docker rm app || true
                docker run -d -p 3000:3000 --name app devops-app
                '''
            }
        }
    }
}

