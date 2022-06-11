pipeline {
  
    agent any
  
    stages {
        stage('clone from github') {
            steps {
                     
             git 'https://github.com/Github_User/Docker-jenkins.git'          
          
            }
        }
        
        stage('Build the dockerfile') {
            steps {
                
                sh 'docker build . -t Dockerhub_User/jenkins:v1.0'
            }
        
    }
             
        stage('push to dockerhub') {
            steps {
                 withCredentials([usernamePassword(credentialsId: 'your_Cred_id', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                sh 'docker login -u ${USERNAME} -p ${PASSWORD}'
                sh ' docker push Dockerhub_User/jenkins:v1.0'
            }
           }
        }   
 }
}
