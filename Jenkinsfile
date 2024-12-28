pipeline {
  agent {Label 'Jenkins_Agent'}
  tools {
    jdk 'java17'
    maven 'maven3'
  }
  stages {
    stage("Cleanup Workspace"){
      steps{
        cleanWs()
      } 
    }
    stage("Checkout from SCM"){
      steps{
        git branch: 'main', credentailsId: 'github', url: 'https://github.com/Manikanta1656/registration-app/'
      } 
    }
    stage("Bulid Application"){
      steps{
          sh "mvn clean package"
      }
    }
    stage("Test Application"){
      steps{
          sh "mvn test"
      }
    }
  }
}
