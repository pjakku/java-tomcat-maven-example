node {

  stage 'build'
  task 'checkout'
  git 'https://github.com/LovesCloud/java-tomcat-maven-example'
  
  task 'Build'
    //// Get maven home path and build
  sh "/opt/maven/apache-maven-3.6.3/bin/mvn clean package -Dmaven.test.skip=true"

  task 'Test-JUnit'
  sh "'/opt/maven/apache-maven-3.6.3/bin/mvn' test surefire-report:report"

  task 'Deploy'     
  sshagent(['Tomcat-jenkins'])
  sh 'scp -o StrictHostKeyChecking=no target/tomcatdeploymnetdemo.war jenkins@35.193.54.220:/opt/tomcat/webapps'

    
}
