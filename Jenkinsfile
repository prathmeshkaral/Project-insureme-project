pipeline {
    agent any
    tools {
        maven 'maven'
    }

    stages {
        stage('git-checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/prathmeshkaral/Project-InsureMe.git'
            }
        }
        
        stage('code-build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        
        stage('Docker-Build') {
            steps {
                sh 'docker build -t prathmesh72/insure-me:i1 .'
            }
        }
        
        stage('Docker-Push') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker_id', passwordVariable: 'passwd123', usernameVariable: 'firstname')]) {
                    sh "docker login -u ${env.firstname} -p ${env.passwd123}"
                    sh 'docker push prathmesh72/insure-me:i1'
                }
            }
        }
        
        stage('Code-Deploy') {
            steps {
                sh 'docker run -d -p 8089:8081 prathmesh72/insure-me:i1'
            }
        }
        
    }
}  
