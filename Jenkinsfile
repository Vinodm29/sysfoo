pipeline {
  
  agent any
  tools {
    maven 'maven'
  }
  
  stages {
    stage('Build') {
      sh 'mvn compile'
    }
  stage('test'){
        sh 'mvn clean test'
      }
  stage('package') {
    sh 'mvn package -DskipTests'
  }
  }

  post {
    always {
      archieveArtifacts artifacts:'**/target/*.war', onlyIfSuccessful:true
    } 

  }    

}
    
      
      
