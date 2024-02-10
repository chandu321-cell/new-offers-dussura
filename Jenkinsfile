pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
      jdk 'Java17'
      maven 'Maven3'  
  }
  stages{
       stage("Cleanup Workspace"){
                 steps {
                 cleanWs()
                 }
       }

    stage("checkout from SCM"){
       steps {
         git branch: 'main', credentialsID: 'github', url: 'https://github.com/chandu321-cell/new-offers-dussura'
       }
    }

      stage("Build Application")
          steps {
            sh "mvn clean package"
          }
    
     }

     stage('Test Application")
           steps {
                sh "mvn test"
           }
       }
  }
}
