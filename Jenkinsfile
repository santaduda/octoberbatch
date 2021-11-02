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
                  withSonarQubeEnv('SonarQube 8.9.3') { 
                  sh "mvn sonar:sonar"
                 }
             }
        }
        stage("Quality Gate") {
            steps {
             // timeout(time: 1, unit: 'HOURS') {
              //  waitForQualityGate abortPipeline: true
              //}
                echo 'test'
            }
          } 
        stage('Upload war to nexus') {
            steps{
                 nexusArtifactUploader artifacts: [
                     [
                         artifactId: 'WebApp', 
                         classifier: '', 
                         file: 'target/Maven-Webapp-1.0.war', 
                         type: 'war'
                     ]
                 ], 
                 credentialsId: 'Nexuslogin', 
                 groupId: 'Demoapp', 
                 nexusUrl: '172.31.22.31', 
                 nexusVersion: 'nexus3', 
                 protocol: 'http', 
                 repository: 'Demoapp', 
                 version: '1.0'
            }          
        }  
    }
}
