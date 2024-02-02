pipeline {
    agent any
    
    tools
    {
       maven "Maven"
    }
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/hbopche/Simple-App.git'
             
          }
        }
        }
     
        
         stage('Build') {
           steps {
             
                sh 'mvn package' 
                sh 'mvn clean install'
          }
        }
}    
