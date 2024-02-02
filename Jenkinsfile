pipeline {
    agent any
    
    tools
    {
       maven "Maven"
       ansible "ansible" 
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
              sh "ansible-playbook build.yml"
          }
        }
}   
}
