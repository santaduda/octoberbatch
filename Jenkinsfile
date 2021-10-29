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
         stage('SonarQube analysis') {
              steps{
                  echo 'hello'
                  withSonarQubeEnv('SonarQube 8.9.3') { 
                  echo 'i am in'
                  sh "mvn sonar:sonar"
                 }
             }
        }
    }
}
