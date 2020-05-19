pipeline {
  
  agent {
    label 'Docker' 
  }
    stages {
  
        stage('Test') {
    
          steps {
            sh 'mvn test'
          }
       }

        stage('Build') {
      
          steps {
             sh 'mvn -B -DskipTests clean package'
          }
        }
     
        stage('Publication du binaire') {

          steps {
            sh "curl -u admin:Shaymin122 --upload-file target/*.war 'http://10.10.20.31:8081/repository/hello_world/app.war'"        
          }

        }
    
      }
  
   
}
