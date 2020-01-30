node {

  stage 'build'
  task 'checkout'
  git 'https://github.com/LovesCloud/java-tomcat-maven-example'
  sleep 1
  task 'Build'
    //// Get maven home path and build
  sh "/opt/maven/apache-maven-3.6.3/bin/mvn clean package -Dmaven.test.skip=true"
  sleep 1
  task 'Test-JUnit'
  sh "'/opt/maven/apache-maven-3.6.3/bin/mvn' test surefire-report:report"
  sleep 1
  task 'Deploy'     
  sshagent(['Tomcat-jenkins'])
  sh 'scp -o StrictHostKeyChecking=no target/tomcatdeploymnetdemo.war jenkins@35.193.54.220:/opt/tomcat/webapps'
  sleep 1
    
}
