//node{
  //    def mvnHome = tool name: 'maven'
stages {  
      stage('Commit'){
            steps{
                 sh label: "Test Result"
                 sh "Yarn ckean"
            }
           // steps{
                  git 'https://github.com/LovesCloud/java-tomcat-maven-example'
            //}
       
      }  
      stage('Integration'){
         git 'https://github.com/LovesCloud/java-tomcat-maven-example'
       
      }  
      stage('Build'){
         //// Get maven home path and build
        sh "${mvnHome}/bin/mvn clean package -Dmaven.test.skip=true"
      }
     stage ('Test-JUnit'){
         sh "'${mvnHome}/bin/mvn' test surefire-report:report"
      }  
    
      stage('Deploy') {     
            sshagent(['Tomcat-jenkins']) {
               sh 'scp -o StrictHostKeyChecking=no target/tomcatdeploymnetdemo.war ec2-user@3.133.161.254:8090:/opt/tomcat/webapps'
                  //jenkins@35.193.54.220
              
          }
         
     }
      
 }
