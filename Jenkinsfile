node{
      stage('Checkout'){
         git 'https://github.com/LovesCloud/java-tomcat-maven-example'
      }  
      stage('Build'){
         //// Get maven home path and build
         def mvnHome =  tool name: 'Maven 3.5.4', type: 'maven'   
         sh "${mvnHome}/bin/mvn package"
      }
      stage ('Test'){
         def mvnHome =  tool name: 'Maven 3.5.4', type: 'maven'    
         sh "${mvnHome}/bin/mvn verify; sleep 3"
      }  
      stage('Deploy') {     
          sshagent(['abeab169-3c7e-4291-98f3-7f190a3d4099']) {            
               sh 'scp -o StrictHostKeyChecking=no target/*.war root@52.90.151.183:/opt/tomcat/webapps'         
           }
     }
      
 }
