pipeline {
    agent any
    tools {
      maven 'maven3'
    }  
    stages{
        stage('Build') {
            steps{
                sh 'mvn clean install -s settings_file.xml'
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
