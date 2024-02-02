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
               script {
                   ansiblePlaybook become: true, installation: 'ansible', inventory: '/var/lib/jenkins/workspace/Project-1/inventories/maven/hosts', playbook: '/var/lib/jenkins/workspace/Project-1/build.yml', vaultTmpPath: ''
               }
}   
}
        stage('Ansible Deploy') {
             steps {
                 script {
                     ansiblePlaybook become: true, installation: 'ansible', inventory: '/etc/ansible/hosts', playbook: '/var/lib/jenkins/workspace/Project-1/main.yml', vaultTmpPath: ''
    }
}
        }
    }
}
