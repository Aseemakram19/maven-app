pipeline {
    agent any
    
    tools{
        maven "Maven3"
    }
       
    stages {
        stage('Git Checkout-github') {
            steps {
             git branch: 'main', url: 'https://github.com/Aseemakram19/maven-app.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
        stage('Create a image') {
            steps {
               sh 'docker build -t aseem1 .'
            }
        }
        stage('Docker Container app') {
            steps {
               sh 'docker run -d -p 9000:8080 -t aseem1'
            }
        }
    }
}