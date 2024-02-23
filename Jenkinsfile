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
        stage ('deploy to tomcat) {
               steps {
           sshagent(['tomcat']) {
                sh 'scp -o StrictHostKeyChecking=no target/*.war ubuntu@13.232.202.25:/opt/tomcat/webapp/webapp.war'
              }
           }
    }
}
}
