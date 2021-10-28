pipeline {
    agent any
    tools {
      maven 'maven3'
    }  
    stages{
        stage('Build') {
            steps{
                sh 'mvn clean'
                sh 'mvn clean package -x'               
            }          
        }  
        stage('sonar') {
            steps{
                echo 'sonar satge'             
            }          
        }
    }
}
