pipeline {
    agent any
    tools {
        maven 'maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/abhipraydhoble/Project-InsureMe.git'
            }
        }

        stage('Code-Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('Docker-Build') {
            steps {
                sh 'docker build -t guru6910/project:p1 .'
            }
        }
        
        stage('Docker-Push') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker_id', passwordVariable: 'passwd', usernameVariable: 'uname')]) {
                    sh "docker login -u ${env.uname} -p ${env.passwd}"
                    sh 'docker push guru6910/project:p1'
                }
            }
        }
        
        stage('Code-Deploy') {
        steps {
           sh 'docker run -d -p 8089:8081 guru6910/project:p1'
        }
      }
    }
}
