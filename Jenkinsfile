pipeline {
  
  agent any
  tools {
    maven 'maven-a'
  }
  
  stages {
    stage('Build') {
      steps {
         sh 'mvn compile'
      }
     
    }
  stage('test'){
    steps{
      sh 'mvn clean test'
    }
        
      }
  stage('package') {
    steps{
      sh 'mvn package -DskipTests'
    }
    
  }
  }

  post {
    always {
      archiveArtifacts artifacts:'**/target/*.war', onlyIfSuccessful:true
    } 

  }    

}
    
      
      
