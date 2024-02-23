pipeline {
    agent any 
    tools {
        maven 'Maven'
    }
    stages {
        
    stage ('Source Composition Analysis') {
      steps {
         //sh 'rm owasp* || true'
         //sh 'wget "https://github.com/plovepsc/webapp/master/owasp-dependency-check.sh" '
         sh 'chmod +x owasp-dependency-check.sh'
         sh 'bash owasp-dependency-check.sh'
         

      }
    }


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
