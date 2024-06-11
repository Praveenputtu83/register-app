pipeline {
    agent { label 'agent' }
    tools {
        jdk 'java17'
      maven 'Maven3'
    }
    stages{
        stage("Cleanup Workspace"){
           steps {
           cleanWs()
           }
    }
    
    stage("Checkout from SCM"){
           steps {
           git branch: 'main', credentialsId: 'git', url: 'https://github.com/Praveenputtu83/register-app'
           }
    }
    
     stage("Build Application"){
          steps {
              withMaven(maven: 'Maven3') {
               sh "mvn clean package"
             }
    }
    
     stage("Test Application"){
            steps {
              sh "mvn test"
            } 
        }
    }
}

