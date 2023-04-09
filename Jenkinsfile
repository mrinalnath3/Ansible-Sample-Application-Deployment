pipeline {
    agent any
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'master', url: 'https://github.com/mrinalnath3/Ansible-Sample-Application-Deployment.git'
             
          }
        }
        
        
        
          stage('Ansible Init') {
            steps {
                script {
                
               def tfHome = tool name: 'Ansible'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
            }
            }
        }
        
        
        
        stage('Ansible Deploy') {
             
            steps {
                 
             
               
               sh "ansible-playbook main.yml -i /home/devops/inventory.txt -become:yes -e '@configs/dev.yml'"

               
            
            }
        }
    }
}
