pipeline {
    agent { label 'agent' }
    tools {
      jdk 'java17'
      maven 'Maven3'
    }
    stages{
        stage("cleanup workspace") {
           steps {
           cleanaWs()
           }
    }
    
    stage("checkout from SCM") {
           steps {
           git branch: 'main', credentialsId: 'git', url: 'https://github.com/Praveenputtu83/register-app'
           }
    }
    
     stage("Build Application") {
             steps {
               sh "mvn clean package"
             }
    }
    
     stage("Test Application") {
            steps {
              sh "mvn test"
            } 
     }
    }
}

