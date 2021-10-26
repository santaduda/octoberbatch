pipeline {
    agent any
    tools {
      maven 'maven3'
    }  
    stages{
        stage('Build') {
            steps{
                sh 'mvn clean package'               
            }          
        }  
        stage('sonar') {
            steps{
                cat "Sonar stage"              
            }          
        }
    }
}
