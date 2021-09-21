pipeline {
    agent {label 'MASTER'}

    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/sirikodali/java11-examples.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn package'
            }
        }
        
    }
    post{
        success{
            archive "**/*.jar"
            junit "**/TEST-*.xml"
        }
    }
}