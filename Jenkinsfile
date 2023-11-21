pipeline{
  agent any
  tools{
    maven 'maven'
  }  

  stages{
    stage("Git Checkout"){
      steps{
         script{
            git branch: 'v24', changelog: false, poll: false, url: 'https://github.com/balu1123/bookstore-example.git'
         } 
      }  
    }

    stage("UNIT Testing"){
      steps{
         sh 'mvn test'
      }  
    }

    stage("Integration Testing"){
      steps{
        sh 'mvn verify -DskipUnitTests'
      }  
    }
  }
}