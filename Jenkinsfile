pipeline {
    agent any 
    tools {
        maven 'Maven'
    }
    stages {
        stage('Initialize') { 
            steps {
                echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOM}"
            }
        }
    }
}
