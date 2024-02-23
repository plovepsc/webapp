pipeline {
    agent any 
    tools {
        maven 'Maven'
    }
    stages {

        stage('build') { 
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('Deploy-To-Tomcat') {
            steps {
           sshagent(['tomcat']) {
                sh 'scp -o StrictHostKeyChecking=no target/*.war root@192.168.0.21:/opt/tomcat/webapps/webapp.war'
              }
           }
    }

    
}
}
