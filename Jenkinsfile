pipeline {
    agent { label 'agent' }
    tools {
      jdk 'java17'
      maven 'Maven3'
    }
    stage("cleanup workspace"){
           steps {
           cleanaWs()
           }
    }
    stage("checkout from SCM"){
           steps {
           git branch: 'main', credentialsId: 'github', url: 'https://github.com/praveenputtu83/register-app'
           }
    }
     stage("Build Application"){
             steps {
               sh "mvn clean package"
             }
     }
     stage("Test Application"){
            steps {
              sh "mvn test"
            } 
     }
}
