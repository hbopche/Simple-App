pipeline {
    agent any
    
    tools
    {
       maven "Maven"
    }
     
    stages {
      stage('checkout') {
           steps {
             script {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/hbopche/Simple-App.git']])
             
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
}
