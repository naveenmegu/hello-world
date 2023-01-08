pipeline {
    agent none

    stages {
        stage('Build') {
        agent {label 'tomcat1'}    
            steps {
               git branch: 'main', url: 'https://github.com/naveenmegu/hello-world'
               sh '''cd /home/ec2-user/jenkins/workspace/agentpipeline
                   mvn clean install'''
            }
        } 
        stage('Deploy') {
          agent {label 'tomcat1'}   
            steps {
           sh '''cd /home/ec2-user/jenkins/workspace/agentpipeline/target
               sudo cp *.war /opt/apache-tomcat-10.0.27/webapps'''

                 
               
            } 
        }  
        
    }
}
