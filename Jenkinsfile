
pipeline {
    agent any
    stages {      
        stage("Copy file to Docker server"){
            steps {
                sh "scp -r /var/lib/jenkins/workspace/66025010-NextJS/* root@43.208.253.87:~/66025010-NextJS"
            }
        }
        
        stage("Build Docker Image") {
            steps {
				ansiblePlaybook playbook: '/var/lib/jenkins/workspace/66025010-NextJS/playbooks/build.yaml'
            }    
        } 
        
        stage("Create Docker Container") {
            steps {
				ansiblePlaybook playbook: '/var/lib/jenkins/workspace/66025010-NextJS/playbooks/deploy.yaml'
            }    
        } 
    }
}
