pipeline {
  agent { label 'Jenkins-Agent'}
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
      stage("Checkout from SCM"){
              steps {
                  git branch: 'main' , crendentialsId: 'github' , url: 'https://github.com/httpzain/DevOps/edit/main/Jenkinsfile'
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
}

