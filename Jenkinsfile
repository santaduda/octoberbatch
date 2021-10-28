pipeline {
    agent any
    tools {
      maven 'maven3'
    }  
    stages{
        stage('Build') {
            steps{
                sh 'mvn clean install -U'
                sh 'mvn clean package'               
            }          
        }  
        stage('sonar') {
            steps{
                echo 'sonar satge'             
            }          
        }
    }
}
