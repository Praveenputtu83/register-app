Pipeline {
    agent { label 'agent' }
    tools {
      jdk 'java17'
      maven 'Maven3'
    }
    stages("cleanup workspace){
           steps {
           cleanaWs()
           }
    }
    stage("checkout from SCM"){
           steps {
           git branch: 'main', credentialsid: 'github', url: 'https://github.com/praveenputtu83/register-app'
           }
    }
     stage("Build Application"){
             steps {
               sh "mvn clean package"
             }
     }
     stage("TestApplication"){
            steps{
              sh "mvn test"
            } 
     }
