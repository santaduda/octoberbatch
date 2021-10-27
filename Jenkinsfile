pipeline {
    agent slave
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
                echo 'sonar satge'             
            }          
        }
    }
}
